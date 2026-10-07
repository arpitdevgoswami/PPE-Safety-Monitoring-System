# 🦺 PPE Safety Monitoring System

A real-time computer vision-based workplace safety monitoring system designed to detect Personal Protective Equipment (PPE) compliance along with fire and smoke hazards.

The system uses YOLO-based object detection to monitor workers through a live webcam or recorded video and identify safety-related conditions such as helmets, safety vests, boots, fire, and smoke.

---

## 📌 Overview

Workplace safety is especially important in environments such as construction sites, factories, warehouses, mines, and industrial facilities.

Traditional safety monitoring mainly depends on manual supervision, which can be difficult to maintain continuously.

This project aims to provide an automated monitoring system that can analyze video footage and identify potential safety violations or hazards in real time.

### The system monitors:

- 👷 Worker / Person
- ⛑️ Helmet
- ❌ No Helmet
- 🦺 Safety Vest
- ❌ No Vest
- 🥾 Boots
- ❌ No Boots
- 🔥 Fire
- 💨 Smoke

The detection results are displayed directly on the video feed using bounding boxes, labels, and safety status indicators.

---

# ✨ Key Features

### 👷 Worker Detection
Detects workers/persons present in the monitored area.

### ⛑️ Helmet Detection
Identifies whether workers are wearing safety helmets.

### 🦺 Safety Vest Detection
Detects safety vests and evaluates whether workers are wearing them.

### 🥾 Boots Detection
Detects safety boots and evaluates the lower-body region of workers.

### 🔥 Fire Detection
Detects visible fire hazards in the monitored environment.

### 💨 Smoke Detection
Detects smoke and generates a warning.

### 🚨 Safety Status
The system provides an overall safety status:

- 🟢 **SAFE** – No major hazard detected
- 🟡 **WARNING** – Smoke or safety violations detected
- 🔴 **DANGER** – Fire detected

### 📹 Multiple Input Modes

The system supports:

- Live webcam
- Recorded video files

### 🎨 Visual Detection
Different objects are represented using different colored bounding boxes and labels, making the system easier to understand during monitoring.

### ⚡ Real-Time Monitoring
The system continuously processes incoming video frames and updates the detected safety conditions.

---

# 🧠 System Architecture

```text
                ┌──────────────────────┐
                │      Video Input     │
                │                      │
                │  Webcam / MP4 Video  │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │     OpenCV Frame     │
                │      Processing      │
                └──────────┬───────────┘
                           │
             ┌─────────────┴─────────────┐
             │                           │
             ▼                           ▼
   ┌──────────────────┐       ┌──────────────────┐
   │    PPE YOLO      │       │ Fire/Smoke YOLO  │
   │      Model       │       │      Model       │
   └────────┬─────────┘       └────────┬─────────┘
            │                          │
            ▼                          ▼
   Person / Helmet /             Fire / Smoke
   Vest / Boots                  Detection
            │                          │
            └─────────────┬────────────┘
                          │
                          ▼
                ┌──────────────────────┐
                │ Safety Status Engine │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │ Monitoring Dashboard │
                │                      │
                │ SAFE / WARNING /     │
                │ DANGER               │
                └──────────────────────┘
