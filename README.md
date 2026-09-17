# Ultrasonic Radar Scanning System using Arduino

An Arduino-based radar-style scanner that combines an HC-SR04 ultrasonic sensor with an SG90 servo motor to continuously sweep a 180° field and report live distance readings — replicating the basic working principle of a radar system using low-cost components.

## 📌 Overview

This project rotates an ultrasonic distance sensor back and forth using a servo motor while continuously measuring the distance to the nearest object at every angle. The angle and distance data is streamed live through the Serial Monitor, simulating a real radar sweep.

## 🎯 Objectives

- Design a working ultrasonic distance-sensing circuit using Arduino UNO
- Control a servo motor for continuous 0°–180° rotational sweeping
- Synchronize sensor readings with servo angle in real time
- Output live angle-distance data through the Serial Monitor

## 🛠️ Hardware Used

| Component | Quantity |
|---|---|
| Arduino UNO | 1 |
| HC-SR04 Ultrasonic Sensor | 1 |
| SG90 Micro Servo Motor | 1 |
| Breadboard | 1 |
| Jumper Wires | As required |
| USB Cable | 1 |

## 💻 Software Used

- Arduino IDE
- Servo.h library (built-in)
- Tinkercad Circuits (for simulation and testing)

## 🔌 Circuit Connections

| Component Pin | Connects To |
|---|---|
| HC-SR04 – VCC | Breadboard + rail (5V) |
| HC-SR04 – GND | Breadboard − rail (GND) |
| HC-SR04 – Trig | Arduino Digital Pin 9 |
| HC-SR04 – Echo | Arduino Digital Pin 10 |
| Servo – Signal | Arduino Digital Pin 11 |
| Servo – VCC | Breadboard + rail (5V) |
| Servo – GND | Breadboard − rail (GND) |
| Arduino – 5V | Breadboard + rail |
| Arduino – GND | Breadboard − rail |

> ⚠️ Note: Only VCC and GND share the breadboard power rails. Trig, Echo, and the Servo signal pin each use a **dedicated direct wire** to their own Arduino pin — never routed through the shared rail.

## ⚙️ How It Works

1. The HC-SR04 sends an ultrasonic pulse via the Trig pin and measures the echo return time via the Echo pin.
2. Distance is calculated using the speed of sound: `Distance = (Duration × 0.034) / 2`
3. The SG90 servo sweeps from 0° → 180° → back to 0°, one degree at a time.
4. At every angle step, a fresh distance reading is taken and printed to the Serial Monitor as `angle,distance`.

## 📄 Code

See [`radar_scan.ino`](./radar_scan.ino) for the full commented Arduino sketch.

## 📊 Sample Output

114,112
113,112
112,112
111,112
110,111
109,110
108,112


## 🚀 Applications

- Obstacle detection for autonomous robots
- Low-cost parking-assist sensors
- Security and intrusion detection
- Educational demonstration of radar/sonar principles

## 🔮 Future Scope

- Add a graphical radar display using Processing
- Add buzzer/LED alerts for close-range objects
- Use multiple sensors for wider, faster coverage
- Add wireless (Bluetooth/Wi-Fi) data transmission

## 👤 Author

**Amar**
23CSE201 – Procedural Programming Using C
Amrita Vishwa Vidyapeetham, Nagercoil Campus
