# Plant Monitoring System with Environmental Sensors

This project is designed to monitor the environmental conditions of a plant, including temperature, humidity, soil moisture, and object detection. It uses multiple sensors like a **DHT11** (temperature and humidity sensor), **soil moisture sensor**, **IR sensor**, and an **LCD display** to provide real-time feedback on the environmental parameters. Additionally, it integrates a **buzzer** and **relay** to control an irrigation system based on the detected soil moisture.

### Features:
- **Temperature and Humidity Monitoring**: The DHT11 sensor measures temperature and humidity levels and displays the values on an LCD screen.
- **Soil Moisture Detection**: A soil moisture sensor detects the moisture level of the soil. If the moisture is low, the system activates a relay to water the plant.
- **Object Detection**: An infrared (IR) sensor detects the presence of an object, and the system triggers a buzzer when an object is detected.
- **Real-time Monitoring**: The system continuously updates and displays the readings on an LCD, while sending the data to the Serial Monitor for debugging.

### Components Used:
- **DHT11**: A temperature and humidity sensor.
- **Soil Moisture Sensor**: Measures the moisture level of the soil.
- **Infrared (IR) Sensor**: Detects the presence of objects (used for object detection).
- **LCD 16x2**: Displays the readings for temperature, humidity, soil moisture, and object detection.
- **Relay**: Controls an external irrigation system (activates the relay when soil moisture is low).
- **Buzzer**: Provides an alert when an object is detected by the IR sensor.
- **Arduino Board** (e.g., NodeMCU or ESP8266): The microcontroller that integrates all the sensors and controls the system.

### Circuit Connections:
- **DHT11 Sensor**: Connect the data pin to **D7**.
- **Soil Moisture Sensor**: Connect the sensor to **pin 8**.
- **Relay**: Connect the relay to **pin 13** to control the irrigation system.
- **IR Sensor**: Connect the sensor to **pin 10**.
- **Buzzer**: Connect the buzzer to **pin 9**.
- **LCD 16x2**: Connect the LCD to **I2C pins (SCL and SDA)** (typically **D1** and **D2** on NodeMCU/ESP8266).

### Code Overview:
The system continuously reads data from the **DHT11** sensor, displays the temperature (in Celsius) and humidity on the **LCD screen**, and sends these values to the **Serial Monitor** for debugging. 

- **Soil Moisture**: The moisture level is detected using a **soil moisture sensor**. If the moisture is too low, the system activates the relay to water the plant.
- **IR Sensor**: The infrared sensor detects objects in the vicinity. If an object is detected, the **buzzer** will be triggered to indicate the presence of the object.
- **LCD Display**: Displays real-time temperature, humidity, soil moisture status, and object detection results.

### Setup Instructions:
1. **Hardware Setup**: 
   - Connect the **DHT11** sensor to **pin D7**.
   - Connect the **Soil Moisture Sensor** to **pin 8**.
   - Connect the **Relay** to **pin 13** (it will control an irrigation system).
   - Connect the **IR Sensor** to **pin 10** (detects objects).
   - Connect the **Buzzer** to **pin 9**.
   - Connect the **LCD 16x2** using I2C to the appropriate **SCL** and **SDA** pins on your microcontroller (D1 and D2 for NodeMCU/ESP8266).

2. **Arduino IDE Setup**:
   - Download and install the **Arduino IDE** if you haven't already.
   - Install the necessary libraries:
     - **DHT sensor library**: Go to **Sketch > Include Library > Manage Libraries**, then search for "DHT sensor library" and install it.
     - **LiquidCrystal I2C library**: Similarly, search for "LiquidCrystal I2C" and install it.
   
3. **Upload Code**:
   - Open the Arduino IDE, paste the provided code, and upload it to the Arduino board.

4. **Monitor Output**:
   - Open the **Serial Monitor** to view the temperature and humidity data, as well as the soil moisture and object detection results.
   - The LCD will continuously update with the current readings.

### Code Functionality:
- **Temperature and Humidity**: The **DHT11** sensor reads the temperature and humidity levels. The temperature is displayed in Celsius, and the humidity is displayed as a percentage. Both values are shown on the **LCD screen**.
  
- **Soil Moisture**: The soil moisture sensor checks the soil's moisture level. If the moisture is low (sensor reads `LOW`), the relay is activated to trigger an irrigation system (e.g., turning on a water pump).
  
- **Object Detection (IR Sensor)**: The **IR sensor** detects if there is an object within its range. If an object is detected (sensor reads `LOW`), the **buzzer** is activated for 5 seconds, and the LCD will display "YES." If no object is detected, the buzzer remains off, and the LCD shows "NO."

- **LCD Display**: The LCD displays real-time readings for **humidity**, **temperature**, and **soil moisture status**. It also shows the result of object detection.

### Example Output:
- **Serial Monitor**:
- H: 65 C: 24

- **LCD Output**:
-H C MOIS OBJ 65 24 HIGH YES
- **H**: Humidity percentage
- **C**: Temperature in Celsius
- **MOIS**: Soil moisture status (HIGH/LOW)
- **OBJ**: Object detection status (YES/NO)

### License:
This project is open-source and available under the [MIT License](LICENSE).

---

This system provides a complete solution for monitoring and automating plant care, including temperature, humidity, soil moisture, and object detection. The system can be used in smart gardening or greenhouse environments to automate irrigation and monitor environmental conditions remotely.
