**Intelligent Plant Disease Detection and Automated Pesticide Spraying System using CNN and IoT**

An AI-powered smart agriculture system that detects tomato leaf diseases using a CNN-based deep learning model and automatically activates a pesticide spraying mechanism using ESP32 and IoT technology. The system performs real-time image processing, sends Telegram alerts, updates an OLED display, and controls a relay-operated pump for automated crop protection.

🚀 Features 

1. Real-time Disease Detection: Uses a ResNet18 CNN model to identify plant diseases from live webcam images.
2. Automated Pesticide Spraying: ESP32 automatically activates a relay-controlled pump when disease confidence exceeds a predefined threshold.
3. IoT Communication: Python application communicates with ESP32 over Wi-Fi using HTTP POST requests and JSON data.
**Telegram Alerts:**

Sends disease detection notifications and captured images directly to Telegram for remote monitoring.
**OLED Monitoring System:**

Displays disease name, confidence percentage, and pump status on an SSD1306 OLED display.
**Image Preprocessing Pipeline:**

Implements Gaussian filtering, HSV segmentation, and morphological operations for improved prediction accuracy.
**Real-time Visual Feedback:**

Displays filtered images, segmented leaves, and disease contour highlighting using OpenCV.

🛠️ Hardware Components

* Microcontroller:
ESP32 Development Board
* Display:
SSD1306 OLED Display (I2C)
* Actuator:
  * Relay Module
  * Mini Water Pump / Pesticide Sprayer
* Sensors & Imaging:
USB Webcam / ESP32-CAM
* Power:
External DC Power Supply
* Miscellaneous:
  * Connecting Wires
  * Breadboard
  * Pipes / Spray Nozzle

📌 Pin Mapping

Component	ESP32 Pin	Description
* Relay Module	GPIO 5	Controls pesticide pump
* OLED SDA	GPIO 21	I2C Data
* OLED SCL	GPIO 22	I2C Clock
  
💻 Software Requirements

The following libraries/frameworks are required:

* Python Libraries
1. torch
2. torchvision
3. opencv-python
4. numpy
5. requests
* Arduino Libraries
1. WiFi.h
2. WebServer.h
3. ArduinoJson.h
4. U8g2lib.h
5. Wire.h

⚙️ Setup Instructions

ESP32 Setup

* Open the Arduino code in Arduino IDE.
* Install required libraries:
  * U8g2
  * ArduinoJson
* Update:
  * Wi-Fi Name
  * Wi-Fi Password
  * Upload the code to ESP32.
* Open Serial Monitor and note the ESP32 IP address.

* Python Setup
* Place the following files in the project folder:
   * resnet_tomato_model.pth
   * classes.pth
   * Update the ESP32 IP address in the Python script.
* Install dependencies:
  * pip install torch torchvision opencv-python numpy requests
  * Run the Python application:
  * python main.py

📊 Logic Flow
1. Image Capture

The webcam continuously captures images of tomato leaves.

2. Preprocessing

The system applies:

Gaussian Blur
HSV Color Segmentation
Morphological Filtering
3. CNN Prediction

The processed image is passed into the ResNet18 model for disease classification.

4. Decision Making

If prediction confidence exceeds 80%:

Disease is confirmed
Telegram alert is generated
Image is uploaded
ESP32 trigger request is sent
5. Automated Spraying

ESP32:

Updates OLED display
Activates relay
Turns ON pesticide pump
Stops spraying after preset duration
6. Monitoring

The system continuously updates:

Disease name
Confidence score
Pump status

on both:

OLED Display
Telegram Notifications

📱 Output Features

Live Disease Detection
Automated Pump Activation
Telegram Alert System
OLED Status Display
Real-time OpenCV Visualization

🔮 Future Improvements

Multi-crop disease detection
Mobile application integration
Cloud database storage
Solar-powered deployment
AI model optimization for edge devices
Smart dosage control system

👨‍💻 Author

N. Deepak Kumar
