# ESP32 Water Usage Tracker

This project is an IoT-based **Water Usage Monitoring System** using ESP32, ThinkSpeak, and MQTT. It measures:
- **Water flow** using a YF-S201 flow sensor.
- **Water tank fills** using a moisture sensor.
- **Water temperature** using a DS18B20 sensor.
- **Predicts future water usage** using AI (Linear Regression).
- **Displays live data** on a web dashboard (ThinkSpeak) and logs data in an Excel file.

## Features
✅ Real-time water usage monitoring  
✅ Predicts future water consumption using AI  
✅ Logs daily data and resets every 24 hours  
✅ Displays live data on **ThinkSpeak**  
✅ Uses **MQTT** to send data to the cloud  
✅ Displays sensor data on **Serial Monitor**

## Hardware Requirements
- **ESP32** (Wi-Fi enabled microcontroller)
- **YF-S201** Water Flow Sensor
- **DS18B20** Temperature Sensor
- **Moisture Sensor**
- **Jumper Wires**
- **5V Power Supply**

## Circuit Connections
| Sensor | VCC | GND | Signal |
|--------|-----|-----|--------|
| **YF-S201 (Water Flow Sensor)** | 5V | GND | GPIO 5 |
| **DS18B20 (Temperature Sensor)** | 5V | GND | GPIO 33 |
| **Moisture Sensor** | 3.3V | GND | GPIO 2 |

## Software Requirements
- **Arduino IDE** with ESP32 board support
- **ThinkSpeak** account
- **MQTT** for cloud data transfer
- **WiFiManager** for dynamic WiFi setup
- **PubSubClient** for MQTT communication
- **OneWire & DallasTemperature** for temperature monitoring

## Installation & Setup
1. **Install ESP32 Board Support in Arduino IDE:**
   - Go to **File > Preferences**
   - Add this URL in **Additional Board Manager URLs**:  
     `https://dl.espressif.com/dl/package_esp32_index.json`
   - Go to **Tools > Board > Boards Manager** and install **ESP32 by Espressif**

2. **Install Required Libraries:**
   - **WiFiManager** (`WiFiManager.h`)
   - **PubSubClient** (`PubSubClient.h`)
   - **DallasTemperature** (`DallasTemperature.h`)
   - **OneWire** (`OneWire.h`)

3. **Set Up ThinkSpeak:**
   - Create an account on [ThinkSpeak](https://thingspeak.com/)
   - Create a new channel and note your **Write API Key**
   - Update the API Key in the Arduino code

4. **Upload Code to ESP32:**
   - Connect ESP32 to PC
   - Select **ESP32 Dev Module** as the board
   - Upload the code

## Expected Output
- **Live Data on ThinkSpeak Dashboard** (Water usage, Tank fills, Temperature)
- **Serial Monitor Output:**
  ```
  Temperature: 25.6 °C, Water Flow Rate: 3.2 L/min, Tank Fills: 2
  Data Sent to ThinkSpeak!
  ```

## Troubleshooting
🔹 **No data on ThinkSpeak?**  
- Check **WiFi credentials** (Use WiFiManager)
- Ensure **MQTT is configured correctly**
- Verify **API Keys** in the code

🔹 **ESP32 not uploading?**  
- Hold the **BOOT button** while uploading
- Check **COM port selection**

## Future Enhancements
🔹 Add **machine learning** to improve predictions  
🔹 Store data in **Google Sheets** or **SQL Database**  
🔹 Integrate **mobile app** for real-time monitoring  


