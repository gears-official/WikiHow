## LDR Module with Arduino

An LDR (Light Dependent Resistor), also known as a photoresistor, is a type of resistor whose resistance changes with the intensity of light. It's commonly used in light sensing applications, such as automatic street lights, dusk-to-dawn switches, and brightness control in electronic devices.

<p align="center">
<img src="https://raw.githubusercontent.com/gears-official/WikiHow/main/Images/H-Bridge.png" width="350" height="350" border="10"/>
</p>


### Operating Principle

The resistance of an LDR decreases as the intensity of light falling on it increases. This property allows it to be used as a sensor to detect changes in light levels.

### Wiring the LDR Module

1. Connect one terminal of the LDR module to the `5V` pin on the Arduino.
2. Connect the other terminal of the LDR module to a resistor (e.g., 10K ohms).
3. Connect the other end of the resistor to any analog pin on the Arduino (e.g., `A0`).
4. Connect the same terminal of the LDR module to the `GND` pin on the Arduino.

### Reading Data from the LDR Module

1. Read the analog voltage from the analog pin connected to the LDR module using the `analogRead()` function.
2. Convert the analog voltage reading to a corresponding light intensity value using a suitable formula or calibration.

### Automatic Light Control

To automatically control a light based on the LDR sensor readings:
- If the LDR detects darkness (low light intensity), turn on the light.
- If the LDR detects light (high light intensity), turn off the light.

### Sample Code

```cpp
#define LDR_PIN A0
#define LIGHT_PIN 13

void setup() {
  Serial.begin(9600);
  pinMode(LIGHT_PIN, OUTPUT);
}

void loop() {
  int sensorValue = analogRead(LDR_PIN);
  
  // Convert analog value to voltage (0-5V)
  float voltage = sensorValue * (5.0 / 1023.0);
  
  // Print voltage value
  Serial.print("Voltage: ");
  Serial.println(voltage);
  
  // If voltage is below a threshold, turn on the light
  if (voltage < 1.0) {
    digitalWrite(LIGHT_PIN, HIGH); // Turn on the light
    Serial.println("Light on");
  } else {
    digitalWrite(LIGHT_PIN, LOW); // Turn off the light
    Serial.println("Light off");
  }
  
  delay(1000);
}
