# Arduino-Class
This repo contains the class materials for the "Arduino Basics" class that I teach at General Electric. It will cover multiple examples intended to teach basic concepts needed to program for Arduinos. All examples are based on the Arduino Uno Rev 3. You can get a "clone" Uno R3 on Amazon for less than $15, here is an example: http://amzn.com/B00SZSFFY0.


## Arduino Software Reference 
We will be using the following Arduino Language Reference page extensively. It defines software structure, variables and functions needed to program for the Arduino.

https://www.arduino.cc/en/Reference/HomePage

<hr>

## Exercise 1: Blink an LED
Connect an LED and current limiting resistor (200 Ohm, blue resistor) to pin 5 of the Arduino Uno. Blink the LED at 1Hz (500ms on, 500ms off). Use a 'function' to perform the actual LED control.

### Concepts
Digital Outputs, Basic Timing, Functions

### Schematic
![Exercise 1](/schematics/exercise_1.png)

<hr>

## Exercise 2: Adjust blink rate with a button
Connect a push button to pin 3 of the Arduino Uno as shown in the schematic. Be sure to add a 10K pulldown resistor to the "arduino side" of the button so that the input is not floating when the button is not pressed(prevents false readings). 

1. Update the LED function to calculate elapsed time using the 'millis()' function instead of using 'delay(500);' in the main loop.

2. Add new code that prints "Press" and "Release" to the serial window each time the button is pressed/released.

3. Finally, modify the LED blink rate each time the button is pressed. The blink rates should match the following table, and after the 4th button press should wrap back around to a 500ms blink rate (as in exercise 1).

Press | Blink Rate (ms)|
--- | --- | --- |
1 | 400 |
2 | 300 |
3 | 200 |
4 | 100 |

### Concepts
Digital Inputs, Advanced Timing, Serial Window

### Schematic
![Exercise 2](/schematics/exercise_2.png)

<hr>

## Exercise 3: Adjust brightness with an analog knob
Connect a potentiometer (analog knob) to analog input 0 (AN0) as shown in the schematic. After connecting the knob, add the following code:

1. Read and print the analog input value to the Serial window every 1 second.

2. Convert the LED output to a PWM output and set the duty cycle (brightness) based on the value of the Analog input. The equation for scaling the brightness is as follows:

`ledBrightness = (unsigned char)(((unsigned long)analogValue * 255)/1023);`

### Concepts
Analog Inputs, PWM Outputs

### Schematic
![Exercise 3](/schematics/exercise_3.png)

<hr>

## Exercise 4: Control a servo with an analog knob
We will only be using the analog knob from the previous exercises. You can remove all components from the right side of your Arduino (button, led, resistors). Connect the servo to the Arduino as shown in the schematic below.

We could write the software to control the servo manually using very specific timing and digital output pulse widths. However, one of the great things about Arduino is that there is a very active community. Chances are, someone has already solved the problem you are trying to tackle. That is the case for servo control. In this example, we will be importing the "Servo" library to control our servo.

The goal of this exercise is to have the servo rotate along with the analog knob (turn knob left, servo goes left proportionally and vice-versa).

### Concepts
Using Libraries, Controlling Servo Motors

### Schematic
![Exercise 4](/schematics/exercise_4.png)

<hr>

## Exercise 5: Control a servo using your breath!


