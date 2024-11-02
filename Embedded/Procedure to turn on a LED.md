1. Identify the [[GPIO]] port (a peripheral) used to connect the LED GPIOA
	1.  GPIA 0x4002 0000 - 0x4002 03FF GPIOA
2. Identify the GPIO pin where the LED is connected
	1. 5
3. Activate the GPIO peripherical ([[Enable the peripheral clock]])
	1. Until you enable the clock for a peripherical, the peripherical is dead and it neither functions nor it takes any configuration value set by you
	2. Once you activate the clock for a peripherical, the periodical is ready to take your configuration and control-related commands or arguments (configuration values).
	3. Note: For some microcontrollers, the peripheral may be ON by default, and you need not do any activation. (you should explore by the device datasheet for reference manual)
4. Configure the GPIO pin mode as output 
	1. Since you are driving an LED (to ON or OFF), the operation mode of the GPIO pin has to be configured as OUTPUT.
5. Write the GPIO pin
	1. 1 (HIGH) to make the GPIO pin state HIGH (3.3V)
	2. 0 (LOW) to make the GPIO pin state LOW (0V)

Check the [[Excercise for STM32F401RET6]]