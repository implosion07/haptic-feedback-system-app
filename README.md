# Haptic Feedback System for Visually Impaired Individuals

A smart assistive wearable system designed to help visually impaired individuals navigate around their surroundings using haptic feedback and real-time object detection along with voice-guidance integrated into a tailored mobile app.



## ✨ Overview

This project presents a haptic feedback-based system that integrates ultrasonic sensors, vibrating motors and an Android mobile application. The hardware setup detects nearby obstacles, sends the data to the mobile app that utilizes SSD MobileNet V1 for Object Detection and provides on screen updates and voice feedback.



## 🚀 Features

* Wearable vest with ultrasonic sensors and vibrating motors
* Real-time obstacle detection and haptic alert
* Mobile app using Flutter with voice feedback
* TensorFlow Lite with SSD MobileNet V1 for on-device object detection
* Bluetooth communication between hardware and app



## 🌐 Tech Stack

### Hardware:

* Arduino UNO
* HC-05 Bluetooth module
* 2 x Ultrasonic Sensors (for distance measurement)
* 2 x Vibrating Motors (for feedback)

### Software:

* Flutter (Mobile App Development)
* TensorFlow Lite (On-device object detection)
* Android/iOS Compatible
* Voice Feedback using flutter\_tts


## 🔧 Working

### Hardware System:

* **Ultrasonic Sensors** detect the distance to nearby obstacles.
* **Arduino UNO** processes the sensor data and sends relevant signals to the vibrating motors.
* **HC-05 Bluetooth** module sends detection signals to the Flutter app.
* **Vibrating Motors** embedded in the vest provide directional haptic feedback.

### Software System:

* Flutter mobile app receives signals via Bluetooth.
* App uses the smartphone camera and TensorFlow Lite to detect and classify nearby objects.
* Voice feedback provided based on detected obstacles and their position.



## 🎓 Getting Started

### Dependencies Required

* Flutter SDK
* Android Studio / Xcode (for Android/iOS deployment)
* Arduino IDE
* Arduino UNO + sensors and Bluetooth module


## 🎨 Hardware Circuit

### Components:

* **Arduino UNO**
* **Ultrasonic Sensors** at left and right positions
* **HC-05 Bluetooth Module** (TX/RX pins)
* **2 Vibrating Motors** controlled by digital pins

### Arduino Pin Connections:

```
Ultrasonic 1: Trig - Pin 2, Echo - Pin 3
Ultrasonic 2: Trig - Pin 7, Echo - Pin 6
Motor 1: Pin 8
Motor 2: Pin 12
Bluetooth TX: Pin 1
Bluetooth RX: Pin 0
```




## 📱 App Installation & Deployment

### 1. Clone Repository:

```bash
git clone https://github.com/vinay10082/haptic-feedback-system
cd haptic-feedback-system
```

### 2. Install Flutter Dependencies:

```bash
flutter pub get
```

### 3. Place TensorFlow Lite Model:

Add your `.tflite` model and `labels.txt` inside `assets/` folder and update `pubspec.yaml`:

```yaml
assets:
  - assets/ssd_mobilenet_v1.tflite
  - assets/labels.txt
```

### 4. Grant Permissions:

Edit AndroidManifest.xml and iOS Info.plist to add necessary permissions for Bluetooth, Camera, Location, and Microphone.

### 5. Build & Run App:

```bash
flutter run
```



## 🪧 Bluetooth Setup and App Connection

### To Establish Connection:

1. **Power on the Arduino device** and pair the HC-05 Bluetooth with the phone.
2. Open the Flutter app.
3. Click on "Connect" inside the app UI to pair with the HC-05 device.
4. The app will show a live camera feed and begin object detection.

### Visual and Haptic Feedback:

* The motors vibrate based on proximity from sensors.
* The app overlays bounding boxes on obstacles and gives voice feedback such as:

  * "Person in right, please go left"
  * "Obstacle ahead, please stop"



## ⚖️ Object Detection Details

* Model Used: SSD Mobilenet v1 (also other models like YoLo in tflite format can be used)
* Deployed using: TensorFlow Lite
* Input Size: 300x300
* Labels: Persons, Cars, Benches, Bottles, Bags, etc.

Bounding box dimensions and distance are calculated based on the width of the detected object in the frame using an approximate linear equation:

```math
distance = (screenwidth - (objectwidth * screenwidth) / 500) - 100
```


## 🧳 Team Members
* Varun Kukreti
* Vinay Kumar Chauhan
* Kartik Thakur
* Sai Shivam Kaushal 


## 👥 Acknowledgements

* Department of Electrical Engineering, National Institute of Technology Hamirpur 
* TensorFlow Lite Team
* Arduino Community
* Flutter Dev Community


## 🚀 Contributions

Contributions and further enhancements to this project are welcome.

---

