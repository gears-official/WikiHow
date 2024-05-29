## Servo Motor with Arduino

A servo motor is a rotary actuator that allows for precise control of angular position. It's commonly used in robotics, RC vehicles, and automation projects where precise movement is required.

<p align="center">
<img src="https://raw.githubusercontent.com/gears-official/WikiHow/main/Images/H-Bridge.png" width="350" height="350" border="10"/>
</p>

### Operating Voltage

Servo motors typically operate at a voltage range of 4.8V to 6V, making them compatible with most Arduino boards.

### Wiring the Servo Motor

1. Connect the servo motor's `VCC` (power) wire to the Arduino's `5V` pin.
2. Connect the servo motor's `GND` (ground) wire to any `GND` pin on the Arduino.
3. Connect the servo motor's `Signal` (control) wire to a PWM-capable digital pin on the Arduino (e.g., `pin 9`).

### Controlling the Servo Motor

1. Include the Servo library in your Arduino sketch.
2. Create a Servo object and attach it to the desired pin (e.g., `Servo myservo; myservo.attach(9);`).
3. Use the `write()` function to set the desired angle of the servo motor (e.g., `myservo.write(90);` for a 90-degree position).
4. Optionally, use the `delay()` function to pause execution for a certain duration.

### Important Consideration: Servo Range

Different servo motors have different operating ranges. Make sure to check the datasheet or specifications of your servo motor to determine its minimum and maximum angle limits.

### Sample Code

```cpp
#include <Servo.h>

Servo myservo;  // Create a servo object

void setup() {
  myservo.attach(9);  // Attach the servo to pin 9
}

void loop() {
  myservo.write(0);   // Move servo to 0 degrees
  delay(1000);        // Wait for 1 second
  myservo.write(90);  // Move servo to 90 degrees
  delay(1000);        // Wait for 1 second
  myservo.write(180); // Move servo to 180 degrees
  delay(1000);        // Wait for 1 second
}
