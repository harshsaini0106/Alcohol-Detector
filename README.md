# Alcohol-Detector


#️⃣ Alcohol Detector IoT Project
An Internet of Things (IoT) project designed to detect the presence of alcohol vapor in the air using a highly sensitive gas sensor (MQ-3) and report the readings in real-time. This system includes a web interface for data visualization and a customizable alert mechanism.


💡 Features
Real-time Monitoring: Continuously reads alcohol concentration data.

Web Server Interface: Hosts a simple, mobile-friendly web page displaying current status and sensor values.

Threshold Alert: Triggers a visual and/or sound alert (buzzer/LED) when the detected alcohol level exceeds a safe threshold.

Hardware Efficiency: Built on the low-cost, Wi-Fi enabled ESP8266 (NodeMCU) microcontroller.

Calibration: Includes logic for basic sensor calibration in fresh air.



🧱 Hardware Components
To build this project, you will need the following components:

Microcontroller: 1 x NodeMCU / ESP8266-12E (or similar Wi-Fi capable board).

Sensor: 1 x MQ-3 Alcohol Gas Sensor.

Display (Optional): 1 x OLED or LCD Display (e.g., 16x2 I2C).

Output: 1 x Buzzer or LED for alerts.

Power: 1 x Micro-USB cable and a power supply.

Connectors: Jumper wires and a Breadboard.


🔌 Circuit Diagram & Setup
The hardware setup is straightforward.
1. MQ-3 Sensor Connection:VCC -> 3.3V (or V-in if using an external power source).
2. GND -> GND.
3. A0 (Analog Output) -> A0 on the NodeMCU.
4. Buzzer/LED Connection:
   Connect the positive leg of the Buzzer/LED to a Digital Pin (e.g., D1/GPIO 5).
   Connect the negative leg to GND.



⚙️ Software Setup & Installation
Follow these steps to get the project running on your board:

1. IDE and Libraries
Download and install the Arduino IDE.

Install the ESP8266 Board Support Package via the Board Manager.

Install necessary libraries via the Library Manager:

ESP8266WiFi (Usually built-in)

ESP8266WebServer (Usually built-in)

If using a display: Adafruit_SSD1306 and Adafruit_GFX.

2. Configuration
Open the main Arduino sketch ([YourProjectName].ino).

Edit the following lines with your Wi-Fi credentials:

C++

const char* ssid = "YOUR_WIFI_SSID";
const char* password = "YOUR_WIFI_PASSWORD";
const int ALCOHOL_THRESHOLD = 700; // Adjust based on calibration
3. Upload
Select the correct board (NodeMCU 1.0 (ESP-12E Module)).

Select the correct Port.

Click the Upload button.



💻 Usage
Once uploaded, the device will:

Connect to the configured Wi-Fi network. The IP address will be printed to the Arduino Serial Monitor.

Start the web server.

Monitor the MQ-3 sensor.

Accessing the Data
Open any web browser on a device connected to the same network.

Navigate to the IP address displayed in the Serial Monitor (e.g., http://192.168.1.105).

The web page will display the current raw Analog Reading and the device Status.

Alert System
If the raw sensor reading is less than ALCOHOL_THRESHOLD, the status will show "Safe / Fresh Air".

If the raw sensor reading is greater than ALCOHOL_THRESHOLD, the status will show "Alcohol Detected! 🚨" and the buzzer/LED will activate.
