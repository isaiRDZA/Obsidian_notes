For example, if your raw analog input is between 0 and 800

```` c++
Serial.print(0); // To freeze the lower limit  
Serial.print(" ");  
Serial.print(1000); // To freeze the upper limit  
Serial.print(" ");  
Serial.println(sensorValue); // To send all three 'data' points to the plotter
```