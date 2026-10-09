# 🛡️ PPE Safety Monitoring System & Digital Twin Platform

An end-to-end, real-time Computer Vision & AI-driven Personal Protective Equipment (PPE) Compliance, Hazard Detection (Fire & Smoke), and 3D Spatial Digital Twin Platform for industrial safety.

---

## 📌 Overview

Workplace safety is critical in high-risk environments such as construction sites, manufacturing plants, chemical zones, and heavy industrial facilities. This platform combines:
1. **YOLO-based Computer Vision Core**: Real-time multi-class object detection (Worker, Hardhat, High-Vis Vest, Safety Boots, Gloves, Goggles, Fire & Smoke).
2. **Interactive 3D Digital Twin & Frontend Dashboard**: High-fidelity React 19 + Three.js application for spatial zone visualization, live CCTV grid simulation, gate access attendance, incident investigation forensics, asset inventory tracking, and predictive analytics.

---

## 🚀 Key Modules & Features

### 1. 🔴 Live Multi-Camera Monitoring (`LiveMonitoringPage`)
- Real-time CCTV streams with AI bounding boxes for PPE compliance.
- Interactive HUD showing live confidence scores, automated alarm alerts, snapshot forensics, and emergency broadcast dispatch.
- Simulation controls: dynamic violation injectors, zone toggling, and incident alert simulations.

### 2. 🌐 3D Spatial Digital Twin (`SpatialZonesPage`)
- Three.js / React Three Fiber interactive 3D factory visualization.
- Orbit camera controls, zone-level hazard highlights (Heavy Fab, Chemical Bay, High Voltage, Furnace Hall), real-time worker spatial pings, and floor plan heatmaps.

### 3. 🚧 Gate Access & Attendance Control (`GateAccessAttendancePage`)
- Automated turnstile biometric + PPE scan verification before access authorization.
- Real-time pass/fail denial logs, RFID verification, and manual barrier override management.

### 4. 👥 Workforce Safety Directory (`WorkforceDirectoryPage`)
- Detailed personnel directories with safety scoring, violation history, active certifications, and emergency contact registry.

### 5. 📦 Smart PPE Asset Vault (`PpeAssetVaultPage`)
- IoT/RFID-tracked safety equipment inventory (helmets, harnesses, respirators).
- Expiration tracking, calibration alerts, battery levels, and maintenance audit logs.

### 6. 🔍 Incident Investigation Hub (`IncidentInvestigationPage`)
- Detailed forensic logs with captured visual evidence, AI confidence breakdowns, supervisor sign-offs, and OSHA-compliant report generation.

### 7. 📈 Predictive Safety Analytics (`PredictiveAnalyticsPage`)
- Time-series compliance forecasting, peak violation hour analysis, and cross-shift safety performance rankings.

### 8. ⚙️ Neural Vision Settings (`NeuralSettingsPage`)
- Configurable inference thresholds, RTSP camera mappings, and alert webhook integrations.

---

## 🧠 AI Detection & System Architecture

```text
                ┌──────────────────────┐
                │      Video Input     │
                │  Webcam / CCTV / MP4 │
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
   Worker / Helmet /              Fire / Smoke
   Vest / Boots / Gloves          Detection
            │                          │
            └─────────────┬────────────┘
                          │
                          ▼
                ┌──────────────────────┐
                │ Safety Status Engine │
                │ (SAFE/WARNING/DANGER)│
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │ SmartPPE Dashboard & │
                │ 3D Spatial Twin      │
                └──────────────────────┘
```

---

## 🛠️ Tech Stack

### Frontend & Digital Twin
- **Framework**: [React 19](https://react.dev/) + [Vite](https://vitejs.dev/) + [TypeScript](https://www.typescriptlang.org/)
- **3D Engine**: [Three.js](https://threejs.org/) + [@react-three/fiber](https://docs.pmnd.rs/react-three-fiber) + [@react-three/drei](https://github.com/pmndrs/drei)
- **Icons & UI**: [Lucide React](https://lucide.dev/) + Custom Dark Glassmorphism CSS Architecture
- **Linter**: [Oxlint](https://oxc.rs/)

### Vision & ML Backend (Python)
- **Object Detection**: Ultralytics YOLOv8 / YOLOv11
- **Computer Vision**: OpenCV
- **Tracking & Geometry**: ByteTrack / Custom Spatial ROI Matching

---

## 🏃 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/arpitdevgoswami/PPE-Safety-Monitoring-System.git
cd PPE-Safety-Monitoring-System
```

### 2. Frontend Dashboard Setup
```bash
# Install dependencies
npm install

# Start local Vite development server
npm run dev

# Build for production
npm run build
```

### 3. Python ML / Vision Pipeline (Optional)
```bash
# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install requirements
pip install ultralytics opencv-python numpy

# Run detection
python main.py
```

---

## 📄 License
This project is licensed under the MIT License.
