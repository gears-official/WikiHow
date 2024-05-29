## DHT11 Sensor with Arduino

The DHT11 is a basic, low-cost digital temperature and humidity sensor. It's easy to use with Arduino and is commonly employed in weather stations, environmental monitoring systems, and HVAC (Heating, Ventilation, and Air Conditioning) applications.


<p align="center">
<img src="https://raw.githubusercontent.com/gears-official/WikiHow/main/Images/H-Bridge.png" width="350" height="350" border="10"/>
</p>

### Operating Voltage

The DHT11 sensor typically operates at a voltage range of 3.3V to 5V, making it compatible with most Arduino boards.

### Wiring the DHT11 Sensor

1. Connect the sensor's `VCC` pin to the `5V` pin on the Arduino.
2. Connect the sensor's `GND` pin to any `GND` pin on the Arduino.
3. Connect the sensor's data pin to a digital pin on the Arduino (e.g., `pin 2`).

### Reading Data from the DHT11 Sensor

1. Include the DHT sensor library in your Arduino sketch.
2. Initialize the sensor object with the appropriate data pin (e.g., `DHT dht(2, DHT11);`).
3. In the `setup()` function, initialize serial communication for debugging purposes (e.g., `Serial.begin(9600);`).
4. In the `loop()` function, read data from the sensor and print it to the serial monitor.

### Important Consideration: Sensor Calibration

The DHT11 sensor may require calibration for accurate temperature and humidity readings. Calibration involves comparing the sensor's readings with a known reference and adjusting the readings accordingly. Keep in mind that environmental factors such as temperature, humidity, and airflow can affect sensor accuracy. Calibration ensures reliable and precise measurements for your application.

### Sample Code

```cpp
#include <DHT.h>

#define DHTPIN 2      // Digital pin connected to the DHT sensor
#define DHTTYPE DHT11 // DHT 11 sensor type

DHT dht(DHTPIN, DHTTYPE);

void setup() {
  Serial.begin(9600);
  dht.begin();
}

void loop() {
  delay(2000); // Wait for 2 seconds between measurements
  
  float temperature = dht.readTemperature(); // Read temperature in Celsius
  float humidity = dht.readHumidity();       // Read humidity
  
  Serial.print("Temperature: ");
  Serial.print(temperature);
  Serial.print("°C\t");
  Serial.print("Humidity: ");
  Serial.print(humidity);
  Serial.println("%");
}
