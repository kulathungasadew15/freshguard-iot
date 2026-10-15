# 🍎 FreshGuard: IoT-Based Smart Fruit Bowl

Welcome to the official repository for **FreshGuard**! 

🚀 **FreshGuard** is a fully completed, ESP32-powered smart storage system that monitors the environment around stored fruit and provides early warnings when conditions need attention. By combining temperature, humidity, gas-trend, and weight sensing with automated ventilation, local alerts, MicroSD logging, and a feature-rich local Wi-Fi dashboard, the system actively helps reduce household food waste.

---

## 📌 Project Overview

The goal of this project is to design, prototype, and deploy an automated IoT fruit bowl that tracks environmental changes and actively responds to prolong freshness.

- **Group:** Group 13
- **Institution:** SLIIT (Year 1, Semester 1)
- **Module:** IT1140 — Fundamentals of Computing
- **Controller:** ESP32 DevKit V1
- **Current Status:** ✅ **Project Completed & Deployed.** All firmware, dashboard files, documentation, and simulation models are fully integrated.

---

## 🎯 Core Objectives & Features

FreshGuard is designed to perform the following core functions:

- 🌡️ **Climate Monitoring:** Track ambient temperature and humidity levels using a **DHT22** sensor.
- 💨 **Gas & VOC Trend Detection:** Observe relative changes in gas and volatile organic compound (VOC) readings using an **MQ-135** sensor.
- ⚖️ **Weight Tracking:** Measure fruit weight dynamically using a **5 kg Load Cell** paired with an **HX711** amplifier.
- 🧠 **Smart Condition Classification:** Evaluate sustained sensor changes and classify storage status as **Fresh**, **Attention**, or **Possible Spoilage**.
- 🔄 **Automated Actuation:** Trigger a **5V ventilation fan** and an **SG90 servo-controlled cover** automatically when storage conditions require intervention.
- 🚨 **Local Status Alerts:** Provide immediate visual and audible feedback via an **RGB LED** and **piezo buzzer**.
- 📊 **Data Logging & Telemetry:** Record historical readings to a **MicroSD card** and stream live metrics directly to a local **Wi-Fi web dashboard**.

> ⚠️ **Important Disclaimer:** FreshGuard monitors storage conditions only. It does not scientifically determine whether fruit is safe to consume, and MQ-135 readings are used strictly as relative gas trends rather than exact gas identification or spoilage measurements.

---

## 🌐 Live Wi-Fi Dashboard

FreshGuard hosts an embedded web interface directly on the ESP32[cite: 1]. When connected to the device's access point or local network (e.g., at `192.168.4.1`), users can access:
- **Real-Time Telemetry:** Live charts for temperature, humidity, gas signals, and fruit weight[cite: 1].
- **Manual Controls:** Override automated fan and cover states with automatic 5-minute timeout safeguards[cite: 1].
- **Calibration Workflows:** Step-by-step clean-air gas baseline setup and scale taring/calibration tools[cite: 1].
- **Data Export & Logs:** Download recent historical CSV logs or browse files directly from the MicroSD card[cite: 1].

The dashboard source file is located in the repository under [`dashboard/index.html`](dashboard/index.html)[cite: 1].

---

## ⚙️ System Operation

The system operates on a continuous sense-evaluate-actuate loop:

1. **Data Acquisition:** The ESP32 polls all connected sensors at regular intervals[cite: 1].
2. **Signal Filtering:** Raw inputs are filtered to discard invalid spikes or sensor noise[cite: 1].
3. **Threshold Evaluation:** Sustained environmental changes are compared against calibrated thresholds[cite: 1].
4. **System Response:** The controller updates the status state, triggers the fan/servo and local alerts if necessary, logs the event to MicroSD, and refreshes the live Wi-Fi dashboard[cite: 1].

---

## 🛠️ Hardware Architecture

The physical design separates the fruit-storage chamber from the electronics base for safety and airflow, utilizing a dedicated MOSFET switching stage to drive the ventilation fan.

| Component | Intended Purpose |
| :--- | :--- |
| **ESP32 DevKit V1** | Main microcontroller, local web server, and Wi-Fi communication[cite: 1] |
| **DHT22** | Temperature and humidity measurements[cite: 1] |
| **MQ-135** | Relative gas/VOC trend monitoring[cite: 1] |
| **5 kg Load Cell + HX711** | Real-time fruit weight measurements[cite: 1] |
| **5V DC Fan + MOSFET Stage** | Active chamber ventilation[cite: 1] |
| **SG90 Servo Motor** | Automated cover opening and closing[cite: 1] |
| **RGB LED & Buzzer** | Local visual status and audible warning outputs[cite: 1] |
| **MicroSD Module & Card** | Local data logging for readings and events[cite: 1] |
| **5V Supply, Breadboard & Jumpers** | Prototype power distribution and interconnections[cite: 1] |

---

## 📈 Final Project Implementation Status

| Subsystem / Area | Status |
| :--- | :--- |
| **RGB LED, DHT22, MQ-135 & HX711** | ✅ Tested and fully operational |
| **Buzzer, Servo & Fan** | ✅ Actuation loops verified |
| **MicroSD Module** | ✅ End-to-end CSV logging confirmed |
| **Wokwi Simulation & Firmware** | ✅ Implemented, tested, and added to the repository |
| **Physical Enclosure & Integration** | ✅ Constructed and fully assembled |
| **Wi-Fi Dashboard (`dashboard/index.html`)** | ✅ Fully integrated and deployed on device[cite: 1] |

---

## 📂 Project Documentation & Assets

Official academic files and source codes are organized as follows:

| Path / File | Description |
| :--- | :--- |
| 🌐 **[`dashboard/index.html`](dashboard/index.html)** | Complete local web dashboard for monitoring and control[cite: 1] |
| 💻 **`firmware/`** | ESP32 source code (`.ino`, `.cpp`, `.h`) |
| 🔌 **`simulation/`** | Wokwi configuration and local simulation files |
| 📄 **[`docs/project-proposal.docx`](docs/project-proposal.docx)** | Problem statement, objectives, hardware selection, and methodology |
| 📊 **[`docs/proposal-presentation.pptx`](docs/proposal-presentation.pptx)** | Executive overview, system architecture, and milestones |
| 📑 **[`docs/progress-report.pdf`](docs/progress-report.pdf)** | System architecture, work breakdown, and test evidence |

---

## 🖥️ Simulation & Circuit Design

🔗 **Live Wokwi Workspace:** [View Referenced Wokwi Project](https://wokwi.com/projects/474755060504718337)

![Proposed Wokwi circuit shown in the progress report](docs/images/wokwi-circuit.png)

📌 See the [Simulation Notes](simulation/README.md) for local reproduction guidelines.

---

## 👥 Project Team (Group 13)

| Team Member | Role |
| :--- | :--- |
| **KULATHUNGA M.A.S.S.** | ⭐ Team Leader |
| **VINOJA H.W.O.** | Team Member |
| **SUBHASHANA T.O.** | Team Member |
| **PERERA M.K.J.C.** | Team Member |
| **SITHUMINI W.T.I.** | Team Member |
| **DAMAYANTHA H.A.E.** | Team Member |

---

## 🗺️ Completed Milestones

- [x] Upload original `.ino` firmware sketches and Wokwi simulation project files.
- [x] Construct the physical two-stage enclosure and integrate all tested hardware components.
- [x] Finalize the Wi-Fi web dashboard and complete end-to-end MicroSD logging tests.
- [x] Calibrate load-cell and gas sensors and fine-tune sustained-reading thresholds.
- [x] Execute complete-system integration tests and document final performance metrics.
