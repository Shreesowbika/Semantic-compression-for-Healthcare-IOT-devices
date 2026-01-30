# Semantic Compression for Healthcare IOT Devices

An intelligent, real-time physiological monitoring system designed to process medical sensor data, detect critical health events (Falls, SPO2 drops, Bradycardia), and optimize data transmission for low-power wearable devices.

## 🚀 Project Overview

In remote patient monitoring, continuous data transmission quickly drains battery life and consumes bandwidth. This project implements a **Smart Alert & Data Archiving System** that reduces data overhead by **98.7%** while ensuring zero latency for critical alerts.

### Key Features
- **Real-time Alerting:** Immediate notification for `SPO2_CRITICAL`, `FALL_DETECTED`, and `HR_CRITICAL_LOW` (Bradycardia).
- **Smart Filtering:** Implements a 2-minute cooldown and an 80% threshold for continuous conditions to prevent alert fatigue.
- **Extreme Data Compression:** Achieved a reduction from ~1.23 MB of raw data to ~15.6 KB of transmitted packets.
- **Adaptive Transmission:** Uses three packet types:
    - ⚠️ **Alerts:** Sent instantly during emergencies.
    - 📊 **Summaries:** Periodic health snapshots (every 30s).
    - 💾 **Archives:** Full state backups at longer intervals (every 300s).

## 📈 Performance Results

| Metric | Value |
| :--- | :--- |
| **Original Data Size** | 1,233.91 KB |
| **Compressed Data Size** | 15.66 KB |
| **Total Data Saved** | 98.7% |
| **Packets Transmitted** | 57 (30 Summaries, 24 Alerts, 3 Archives) |

## 🛠️ Technical Implementation

- **Data Processing:** Python / Pandas
- **Logic:** Windowed thresholding and state-based cooldowns.
- **Output:** Structured transmission log (`packet_transmission_log.csv`) and visualization of sensor trends.

## 📂 File Structure
- `cn_project_new.ipynb`: Main project logic and data processing.
- `packet_transmission_log.csv`: Log of all transmitted data packets.
