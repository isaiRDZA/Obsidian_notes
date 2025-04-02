```c++
/* Code to target the UNO R4 WiFi board. This example will plot the PulseSensor signal scaled to fit on the LED Matrix! Check out the PulseSensor Playground Tools for explaination of all user functions and directives. https://github.com/WorldFamousElectronics/PulseSensorPlayground/blob/master/resources/PulseSensor%20Playground%20Tools.md Copyright World Famous Electronics LLC - see LICENSE Contributors: Joel Murphy, https://pulsesensor.com Yury Gitman, https://pulsesensor.com Bradford Needham, @bneedhamia, https://bluepapertech.com Licensed under the MIT License, a copy of which should have been included with this software. This software is not intended for medical use. */ 

/* Include the PulseSensor Playground library to get all the good stuff! The PulseSensor Playground library will decide whether to use a hardware timer to get accurate sample readings by checking what target hardware is being used and adjust accordingly. You will see a warning during compilation that notes if a hardware timer is being used or not. */ 

#include <PulseSensorPlayground.h> 
#include "WiFiS3.h" 
#include "secrets.h" 

/* The format of our output. Set this to PROCESSING_VISUALIZER if you're going to run the Processing Visualizer Sketch. See https://github.com/WorldFamousElectronics/PulseSensor_Amped_Processing_Visualizer Set this to SERIAL_PLOTTER if you're going to run the Arduino IDE's Serial Plotter. */ 

const int OUTPUT_TYPE = SERIAL_PLOTTER; 
char ssid[] = SECRET_SSID; // your network SSID (name) 
char pass[] = SECRET_PASS; // your network password (use for WPA, or use as key for WEP) 
int status = WL_IDLE_STATUS; 

// ThingSpeak API 
const char* server = "api.thingspeak.com"; 
const String apiKey = "NVG0ATAYMQ1ZZGWE"; // Replace with your ThingSpeak Write API Key 
const int port = 80; // 
WiFi client WiFiClient client; 

/* Pinout: 
PULSE_INPUT = Analog Input. Connected to the pulse sensor purple (signal) wire. 
PULSE_BLINK = digital Output. Connected to an LED (and 1K series resistor) that will flash on each detected pulse. PULSE_FADE = digital Output. PWM pin onnected to an LED (and 1K series resistor) that will smoothly fade with each pulse. NOTE: PULSE_FADE must be a pin that supports PWM. Do not use pin 9 or 10, because those pins' PWM interferes with the sample timer. 
THRESHOLD should be set higher than the PulseSensor signal idles at when there is nothing touching it. The expected idle value should be 512, which is 1/2 of the ADC range. To check the idle value open a serial monitor and make note of the PulseSensor signal values with nothing touching the sensor. THRESHOLD should be a value higher than the range of idle noise by 25 to 50 or so. When the library is finding heartbeats, the value is adjusted based on the pulse signal waveform. THRESHOLD sets the default when there is no pulse present. Adjust as neccesary. */ 
const int PULSE_INPUT = A0;
const int PULSE_BLINK = LED_BUILTIN; 
const int PULSE_FADE = 5; 
const int THRESHOLD = 550; // Adjust this number to avoid noise when idle 

/* All the PulseSensor Playground functions. */ 

PulseSensorPlayground pulseSensor;

int count = 0; 
/* library and variables used to plot on the LED matrix */ 
#include "Arduino_LED_Matrix.h" 
ArduinoLEDMatrix plotter; 
int maxX = 11; 
int maxY = 7; 
int minX = 0; 
int minY = 0; 
int pulseSignal; byte frame[8][12] = { // frame array is [y][x] 
{ 0,0,0,0,0,0,0,0,0,0,0,0 }, 
{ 0,0,0,0,0,0,0,0,0,0,0,0 }, 
{ 0,0,0,0,0,0,0,0,0,0,0,0 }, 
{ 0,0,0,0,0,0,0,0,0,0,0,0 }, 
{ 0,0,0,0,0,0,0,0,0,0,0,0 }, 
{ 0,0,0,0,0,0,0,0,0,0,0,0 }, 
{ 0,0,0,0,0,0,0,0,0,0,0,0 },
{ 0,0,0,0,0,0,0,0,0,0,0,0 } 
}; 
void setup() { 
/* Use 115200 baud because that's what the Processing Sketch expects to read, and because that speed provides about 11 bytes per millisecond. If we used a slower baud rate, we'd likely write bytes faster than they can be transmitted, which would mess up the sample reading calls, which would make the pulse measurement not work properly. */ 
Serial.begin(115200); 
while (!Serial) { 
; // wait for serial port to connect. Needed for native USB port only 
} 
// check for the WiFi module: 
if (WiFi.status() == WL_NO_MODULE) 
{ 
Serial.println("Communication with WiFi module failed!"); // don't continue 
while (true); 
} 
String fv = WiFi.firmwareVersion(); 
if (fv < WIFI_FIRMWARE_LATEST_VERSION) 
{ 
Serial.println("Please upgrade the firmware"); 
} 
// attempt to connect to WiFi network:
while (status != WL_CONNECTED) 
{ 
Serial.print("Attempting to connect to SSID: "); 
Serial.println(ssid); 
// Connect to WPA/WPA2 network. Change this line if using open or WEP network: 
status = WiFi.begin(ssid, pass); 

// wait 10 seconds for connection: 
delay(10000); 
} 
//server.begin(); 
// you're connected now, so print out the status: 
printWifiStatus(); 

// Configure the PulseSensor manager.
pulseSensor.analogInput(PULSE_INPUT); 
pulseSensor.blinkOnPulse(PULSE_BLINK); 
pulseSensor.fadeOnPulse(PULSE_FADE); 
pulseSensor.setSerial(Serial); 
pulseSensor.setOutputType(OUTPUT_TYPE); pulseSensor.setThreshold(THRESHOLD); 

// Now that everything is ready, start reading the PulseSensor signal.
if (!pulseSensor.begin()) { 
/* PulseSensor initialization failed, likely because our particular Arduino platform interrupts aren't supported yet. If your Sketch hangs here, try PulseSensor_BPM_Alternative.ino, which doesn't use interrupts. */ 
for(;;) { 
// Flash the led to show things didn't work. 
digitalWrite(PULSE_BLINK, LOW); 
delay(50); 
Serial.println('!'); 
digitalWrite(PULSE_BLINK, HIGH); 
delay(50); 
} 
} 
// start up the LED matrix so we can control it. plotter
.begin(); 
} 
void loop() { 
/* Wait a bit. We don't output every sample, because our baud rate won't support that much I/O. */ 
delay(20); 

// write the latest sample to Serial. 
//pulseSensor.outputSample(); 

/* Get the latest PulseSensor signal value and scale it to fit the LED matrix. advanceLEDplotter shifts the data history to the left. */ 
pulseSignal = pulseSensor.getLatestSample(); // copy the latest sample value 
pulseSignal = 1023 - pulseSignal; // invert for matrix disply to show with X axis along power and analog pins 
pulseSignal = pulseSignal/128; // scale to the LED matrix height
pulseSignal = constrain(pulseSignal, minY, maxY); // limit the singal so it won't get out of the frame 
advanceLEDplotter(); 
plotter.renderBitmap(frame, 8, 12); 

/* If a beat has happened since we last checked, write the per-beat information to Serial. */ 
if (pulseSensor.sawStartOfBeat()) { 
pulseSensor.outputBeat(); 
//Serial.print(","); 
Serial.println(pulseSensor.getBeatsPerMinute()); 
//Serial.print(","); 
} 
count++; if (count%250==0) { int bpm = pulseSensor.getBeatsPerMinute(); String input = String(bpm); //input.trim(); 
// Remove any extra spaces or newline characters 

Serial.print("Sending data to ThingSpeak: "); 
Serial.println(input); 
if (sendDataToThingSpeak(input)) { 
Serial.println("Data sent successfully!"); 
	} 
else { 
Serial.println("Failed to send data."); 
		} 
	}
} /* New PulseSensor data comes in on the right of the plotter. The 'right' is the matrix edge along the Qwiic/STEMMA connector edge of the board. */ 
void advanceLEDplotter(){ 
for(int y=0; y<=maxY; y++){ 
	for(int x=0; x<=maxX-1; x++){ 
		if(frame[y][x+1] == 1){ 
			frame[y][x] = 1; frame[y][x+1] = 0; 
			} 
		else { 
		frame[y][x] = 0; 
		} 
	} 
} 
frame[pulseSignal][maxX] = 1; 
} 
void printWifiStatus() { 
// print the SSID of the network you're attached to: 
Serial.print("SSID: "); 
Serial.println(WiFi.SSID()); 

// print your board's IP address: 
IPAddress ip = WiFi.localIP(); 
Serial.print("IP Address: "); 
Serial.println(ip); 

// print the received signal strength: 
long rssi = WiFi.RSSI(); 
Serial.print("signal strength (RSSI):"); 
Serial.print(rssi); Serial.println(" dBm"); 
} 

bool sendDataToThingSpeak(String value) { 
if (client.connect(server, port)) { 
// Create HTTP GET request 
String url = "/update?api_key=" + apiKey + "&field1=" + value;
client.print(String("GET ") + url + " HTTP/1.1\r\n" + "Host: " + server + "\r\n" + "Connection: close\r\n\r\n"); 

// Wait for response 
unsigned long timeout = millis(); 
while (client.available() == 0) { 
if (millis() - timeout > 5000) { 
Serial.println(">>> Client Timeout!"); 
client.stop(); 
return false; 
} 
} 

// Read and print response (optional) 
while (client.available()) { 
String line = client.readStringUntil('\r'); 
Serial.print(line); 
} 
client.stop(); 
return true; 
} 
else { 
Serial.println("Connection to ThingSpeak failed.");
return false; 
} 
}
```

