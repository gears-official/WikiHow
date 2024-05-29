## MQ2 Smoke Sensor with Arduino

The MQ2 smoke sensor is commonly used to detect various gases, including smoke, methane, propane, and butane. It's widely used in gas leakage detection systems, smoke alarms, and air quality monitoring devices.

<p align="center">
<img src="https://raw.githubusercontent.com/gears-official/WikiHow/main/Images/H-Bridge.png" width="350" height="350" border="10"/>
</p>

### Operating Voltage

MQ2 smoke sensors typically operate at a voltage range of 5V to 12V, making them compatible with most Arduino boards.

### Wiring the MQ2 Smoke Sensor

1. Connect the sensor's `VCC` (power) wire to the Arduino's `5V` pin.
2. Connect the sensor's `GND` (ground) wire to any `GND` pin on the Arduino.
3. Connect the sensor's `AOUT` (analog output) wire to an analog pin on the Arduino for analog readings.
4. Optionally, connect the sensor's `DOUT` (digital output) wire to a digital pin on the Arduino for digital readings.

### Reading Data from the MQ2 Smoke Sensor

1. Read the analog signal from the `AOUT` pin using the `analogRead()` function for analog readings.
2. Optionally, read the digital signal from the `DOUT` pin using the `digitalRead()` function for digital readings.

### Important Consideration: Calibration

Calibrate the MQ2 smoke sensor according to the specific gases you want to detect. This involves exposing the sensor to known concentrations of gases and adjusting the sensitivity accordingly.

### Sample Code

```cpp
// Analog MQ2 Smoke Sensor Example

#define SMOKE_SENSOR_PIN A0

void setup() {
  Serial.begin(9600);
}

void loop() {
  int sensorValue = analogRead(SMOKE_SENSOR_PIN);
  
  Serial.print("Smoke level: ");
  Serial.println(sensorValue);
  
  delay(1000);
}
