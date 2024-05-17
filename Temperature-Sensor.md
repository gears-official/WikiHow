
# Temperature Sensor

Temperature sensors are devices that detect and measure coldness and heat and convert it into an electrical signal

<p align="center">
<img src="https://raw.githubusercontent.com/gears-official/WikiHow/main/Images/Temprature%20Sensor%20Lm35.png" width="300px" height=300px" >
</p>

Temperature sensors are essential components in a wide range of applications, from home automation systems to industrial machinery. These sensors provide accurate readings of temperature changes, enabling systems to respond appropriately. In this article, we'll delve into the *LM35* temperature sensor, a popular choice for hobbyists and professionals alike, due to its simplicity, precision, and compatibility with microcontrollers like Arduino. Additionally, we will explore different types of temperature sensors and their unique features.

## Types of Temperature Sensors

### 1. Thermocouples

**Key Features:**

- Wide Temperature Range: Capable of measuring extreme temperatures, from -200°C to +1800°C, depending on the type.

- Durability: Strong and suitable for harsh environments.

- Self-Powered: Generate a voltage proportional to temperature without needing an external power source.

**Applications:** Industrial furnaces, kilns, gas turbine exhaust, diesel engines.

### 2. Thermistors

**Key Features:**

- High Sensitivity: Can detect small temperature changes with high precision.

- Limited Range: Typically measure temperatures from -100°C to +300C.

- Non-Linear Response: Their resistance changes non-linearly with temperature.

**Applications:** Medical devices, automotive temperature sensors, consumer electronics.

### 3. Infrared Sensors

**Key Features:**

- Non-Contact Measurement: Can measure temperature from a distance by detecting infrared radiation.

- Rapid Response: Provide quick temperature readings.

- Variable Accuracy: Depending on the target and environmental conditions.

**Applications:** Body temperature measurement, industrial equipment monitoring, electrical inspections.

### 4. Semiconductor Sensors

**Key Features:**

- Integrated Circuits: Combine temperature sensing with signal conditioning, often providing digital output.

- Narrow Range: Typically measure temperatures between -40°C and +150°C.

- Cost-Effective: Affordable and easy to integrate with digital systems.

**Applications:** Computer hardware, environmental monitoring, consumer electronics.


## The LM35 Temperature Sensor

The LM35 is an analog temperature sensor that provides a linear voltage output proportional to the temperature. It's widely used due to its accuracy and ease of use with microcontrollers like Arduino.

### Key Features

- Linear Output: The output voltage is directly proportional to the temperature in degrees Celsius.

- High Precision: Accurate to within ±0.5°C at room temperature.
Simple Interface: Requires only three connections (VCC, GND, and output).

- Low Self-Heating: The LM35 draws only 60 μA from the supply, leading to very low self-heating (less than 0.1°C in still air).

- Wide Operating Range: Suitable for temperatures from -55°C to +150°C.

## Wiring the LM35 Temperature Sensor

Wiring the LM35 to an Arduino is straightforward:

**Connect the Sensor:**

- VCC (Power) to the 5V pin on the Arduino.
- GND (Ground) to the GND pin on the Arduino.
- OUT (Output) to an analog input pin (A0) on the Arduino.

## Controlling the LM35 with Arduino

To read the temperature data from the LM35 sensor, you can use a simple analogRead function in Arduino.

```cpp
// Define the analog pin connected to the LM35 output
const int sensorPin = A0;

void setup() {
  // Start serial communication
  Serial.begin(9600);
}

void loop() {
  // Read the analog value from the sensor
  int sensorValue = analogRead(sensorPin);

  // Convert the analog value to voltage
  float voltage = sensorValue * (5.0 / 1023.0);

  // Convert the voltage to temperature in Celsius
  float temperatureC = voltage * 100.0;

  // Print the temperature in Celsius to the serial monitor
  Serial.print("Temperature: ");
  Serial.print(temperatureC);
  Serial.println(" °C");

  // Wait for a second before the next reading
  delay(1000);
}
```
### Explanation of the Code

- **Initialization:** Defines the analog pin connected to the LM35 and starts serial communication.

- **Reading Sensor Value:** Reads the analog value from the sensor pin.

- **Voltage Conversion:** Converts the analog value to voltage.

- **Temperature Calculation:** Converts the voltage to temperature in Celsius.

- **Output:** Prints the temperature to the serial monitor.

### Applications of LM35

Temperature sensors like the LM35 are utilized in various applications:

- **Home Automation:** Regulating heating and cooling systems.
Weather Stations: Monitoring environmental conditions.

- **Industrial Processes:** Ensuring machinery operates within safe temperature ranges.

- **Food Storage:** Maintaining proper storage temperatures to ensure food safety.

- **Wearable Devices:** Measuring body temperature for health monitoring.


### Conclusion

The LM35 temperature sensor is a versatile and reliable component for temperature measurement tasks. Its linear output, ease of use with Arduino, and high accuracy make it ideal for numerous applications. Whether you're working on a simple home project or an industrial system, the LM35 provides the precision and reliability you need. By following the wiring instructions and using the provided Arduino code, you can quickly integrate this sensor into your own projects. Understanding the various types of temperature sensors can also help you choose the right sensor for your specific needs.


