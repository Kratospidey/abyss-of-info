---
{"dg-publish":true,"permalink":"/college/sem-iv/physics/arduino-microprocessor/"}
---

# Project Report 

## Intro:
An Arduino Uno R3 is a small computer that you can use to control electronic devices and make them interact with their environment. It is called a "microprocessor" because it is a very small and simple central processing unit, or CPU, that can read and execute instructions stored in memory. The Arduino Uno R3 has a number of input and output pins that you can use to connect sensors, actuators, and other devices to it. You can use it to read data from sensors, such as temperature or light level, and use that data to control other devices, such as turning on a light or moving a motor. 

The Arduino Uno R3 is programmed using a language called C++, which is a popular programming language for building all kinds of applications. You can use the Arduino Integrated Development Environment (IDE) to write and upload your code to the Arduino, which will then execute your instructions. 

Overall, the Arduino Uno R3 is a very versatile and powerful tool for building all sorts of electronic projects, and it is widely used by hobbyists, educators, and professionals alike.


## Use cases:
A few useful applications for the Arduino Microprocessor are listed below:
1. Home automation system: You can use an Arduino Uno to control lights, appliances, and other devices in your home. You could connect the Arduino to a network of smart outlets or switches, and then use the Arduino to turn these devices on or off as needed. For example, you could create a program that turns off all of the lights in the house when you go to bed, or that turns on the coffee maker when you wake up in the morning. You could even connect the Arduino to sensors, such as motion detectors or door sensors, to create a system that can respond to your presence or absence.
2. Automatic plant watering system: Using an Arduino Uno and a soil moisture sensor, you could create a system that waters your plants only when they need it. The Arduino could read the soil moisture sensor and turn on a watering valve when the soil is dry, and turn it off when the soil is moist. You could also set up a program that allows you to specify how often the plants should be watered, and have the Arduino adjust the watering schedule based on the weather or the time of year.
3. Automatic pet feeder: You could use an Arduino Uno and a servo motor to create a device that dispenses food for your pets at a set time every day. The Arduino could control the servo motor, which would open a hatch to release a measured amount of food into a dish. You could set up the Arduino to dispense the food at the same time every day, or you could create a program that allows you to specify different feeding times for different days of the week.
4. Temperature control system: Using an Arduino Uno and a temperature sensor, you could create a system that turns on a fan or air conditioning unit when the temperature in a room gets too hot, and turns it off when the temperature drops to a comfortable level. The Arduino could read the temperature sensor and turn the fan or air conditioning unit on or off as needed to maintain a comfortable temperature. You could also set up a program that allows you to specify a range of acceptable temperatures, and have the Arduino adjust the fan or air conditioning as needed to stay within that range


## Use case for one application of the Arduino:
Knock Detector:
It detects vibrations that surpass a specific threshold.

## Requirements:
1. A Piezoelectric sensor
2. An Arduino Uno R3 Microprocessor
3. A LED
4. A Breadboard
5. Connectors
6. 1 Mega-Ohm Resistor

## Set-Up Instructions:
1. Attach the positive and the negative terminals of the piezoelectric sensor to the breadboard.
2. Attach a connector from the same line as the positive terminal of the piezoelectric sensor on the breadboard to analog input 0 in the Arduino microprocessor.
3. Attach a connector from the same line as the negative terminal of the piezoelectric sensor on the breadboard to ground terminal in the Arduino microprocessor.
4. Attach the 1 Mega-Ohm resistor from the same lines as the positive terminal of the piezoelectric sensor to the negative terminal of the piezoelectric sensor on the breadboard.
5. Plug in the wire attached to the Arduino Microprocessor into your computer and run the Arduino Integrated Development Environment.
6. Upload the Program that handles the logic for detecting vibration onto the microprocessor.
7. Insert an LED on Pin 13 of the Arduino microprocessor.

With this, the steps for setting up the Knock Detector are complete.

## Explanation:
The Piezoelectric Sensor will detect vibrations and will output a voltage.
This voltage will go to the breadboard and consequently, the Arduino microprocessor.
If the voltage exceeds a certain threshold, the LED’s state will be inverted, turning it ON or OFF.
