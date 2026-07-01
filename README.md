# 🏆 Autonomous & Web-Controlled 4WD Robot | Electronics Department Robotics Competition CHAMPION

An autonomous and remote-view 4-wheel drive (4WD) wheeled robot built for the Electronics Department Robotics Competition, where it took **1st Place / Champion**. The robot features a custom hardware build designed to look like the iconic **SpongeBob SquarePants Patty Wagon**, perfectly blending robust hardware engineering with an iconic creative aesthetic.

## 🚀 Project Overview

This repository contains the complete firmware, web interface, and hardware control logic for our championship-winning robot. Driven entirely by an **ESP32 Camera module**, the system serves its own wireless control dashboard, allowing operators to monitor live video telemetry and pilot the vehicle from anywhere within network range.

### Key Features
* **🏆 Championship Winner:** Awarded 1st Place in the Electronics Department Robotics Competition.
* **📷 First-Person View (FPV) Live Stream:** High-performance video streaming handled over an MJPEG HTTP server (`/stream`), allowing effective steering even when completely out of line-of-sight.
* **🌐 Self-Hosted Web Dashboard:** Serves a responsive HTML/CSS/JS control dashboard directly from the ESP32. Utilizes asynchronous AJAX requests (`XMLHttpRequest`) for zero-latency, real-time locomotion tracking.
* **⚡ Hardware-Level PWM Motor Control:** Configured native ESP32 `ledc` peripherals running an 8-bit timer at 2000Hz across 4 hardware channels for highly fluid multi-directional movement.
* **💡 Toggleable Night-Vision Headlight:** Direct software mapping to the onboard flash LED via hardware PWM, controllable remotely from the web UI to illuminate dark testing environments.
* **🔋 High-Endurance Power:** Driven by a rechargeable **12V Lithium-Ion battery**, ensuring consistent voltage and high current output for the 4WD motors during peak competition runs.

---

## 🛠️ Tech Stack & Hardware

* **Language:** C++ / Arduino
* **Platform:** Arduino IDE
* **Frameworks:** `esp_http_server.h`, `esp_camera.h`, `driver/ledc.h`
* **Microcontroller:** ESP32-CAM Development Board
* **Power System:** Rechargeable 12V Lithium-Ion Battery
* **Architecture:** 4WD Chassis, DC Gear Motors, Motor Driver Module.

---

## 👤 My Role: Sole Programmer

I was entirely responsible for the **software architecture, UI design, and firmware programming** of this project. Working solo on the software side, my core accomplishments included:
* **Asynchronous Web Architecture:** Built the twin-port HTTP server topology to separate core API command routing (Port 80) from heavy MJPEG camera stream processing (Port 81) to eliminate control latency.
* **Kinematics & Duty Cycle Tuning:** Developed customized movement arrays (`robot_fwd`, `robot_fwd_left`, etc.) utilizing underlying ESP32 ESP-IDF hardware abstractions to cleanly drive directional motor pairs.
* **UI/UX Development:** Implemented an inline, mobile-optimized CSS touch-button layout featuring dual execution loops (`onmousedown` and `ontouchstart`) to prevent interface locking on touchscreen controllers.
* **System Integration:** Debugged hardware-to-software bottlenecks, optimizing data block delivery times for real-time responsiveness during competition trials.
