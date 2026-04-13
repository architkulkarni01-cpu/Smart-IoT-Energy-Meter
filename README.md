# Smart Electricity Energy Meter using ESP32 & Blynk 2.0

> IoT-Based Real-Time Electricity Monitoring System — ESP32 + ZMPT101B + SCT-013 + Blynk 2.0

---

## Overview

This project presents a smart electricity energy meter that monitors real-time electrical parameters — voltage, current, power, and energy consumption — using the ESP32 microcontroller. Data is transmitted wirelessly to the Blynk 2.0 cloud platform and visualized on a mobile dashboard from anywhere. Energy data is also stored in the ESP32's EEPROM to ensure continuity during power outages.

Designed as a low-cost, IoT-ready prototype for smart metering applications.

---

## Key Features

- Real-time monitoring of Voltage (V), Current (A), Power (W), and Energy (kWh)
- Wireless data upload to Blynk 2.0 cloud over Wi-Fi
- Mobile dashboard with gauge-style live readouts
- EEPROM-based data storage — no data loss during power outages
- Non-invasive current sensing (SCT-013) — no need to cut live wires
- EmonLib-based true RMS calculations for accurate AC measurements

---

## Circuit Diagram & Hardware Setup

![Circuit Diagram](images/circuit_diagram.png)

![Hardware Setup](images/hardware_setup.png)

The ESP32 interfaces with the ZMPT101B voltage sensor and SCT-013 current sensor. The voltage sensor connects directly to an analog GPIO pin, while the current sensor uses a burden resistor and decoupling capacitor circuit before connecting to the ADC.

---

## Hardware Components

| Component | Specification |
|---|---|
| **ESP WROOM-32** | Dual-core 240 MHz, Wi-Fi, Bluetooth, 12-bit ADC |
| **ZMPT101B Voltage Sensor** | Up to 250V AC, onboard op-amp, 5–30V supply |
| **SCT-013 Current Sensor** | 0–30A AC, non-invasive clamp, 1800:1 turn ratio, ±2–3% |
| **Burden Resistor** | 100Ω — converts SCT-013 output to readable voltage |
| **Bias Resistors** | 2× 10KΩ — midpoint biasing for ADC input |
| **Decoupling Capacitor** | 10µF — filters noise on current sensor output |

### Sensor Photos

| ZMPT101B Voltage Sensor | SCT-013 Current Sensor |
|---|---|
| ![ZMPT101B](images/zmpt101b_voltage_sensor.jpg) | ![SCT-013](images/sct013_current_sensor.jpg) |

---

## Blynk 2.0 Dashboard

![Blynk Dashboard](images/blynk_dashboard.jpg)

The mobile dashboard displays live gauge readouts for:
- **Voltage** (0–300V)
- **Current** (0–300A)
- **Power** (0–1000W)
- **Energy Units** (0–10 kWh)
- **Total Cost**

---

## Software & Libraries

| Library | Purpose |
|---|---|
| **EmonLib** | True RMS voltage and current calculations using continuous background sampling |
| **Blynk** | Wi-Fi connectivity and cloud data visualization on mobile |
| **EEPROM** | Persistent energy data storage across power cycles |

---

## Repository Structure

```
├── firmware/        # Arduino sketch (main.ino)
├── hardware/        # Wiring details and component specs
├── images/          # Circuit diagram, hardware setup, sensor photos, Blynk dashboard
├── results/         # Live dashboard screenshot and observations
└── README.md
```

---

## Future Scope

- Integration with renewable energy sources (solar/wind)
- AI-based personalized energy-saving recommendations
- Secure communication protocols (TLS/MQTT)
- Smart home integration for automated load control
- Smart grid connectivity for dynamic pricing and energy trading

---

## Authors

**Samarth More** (PRN: 1032221224) & **Archit Kulkarni** (PRN: 1032221176)  
Department of Electrical and Electronics Engineering  
Dr. Vishwanath Karad MIT World Peace University, Pune
