# Electrospinning_Device
# Design of Integrated Low-Cost Electrospinning Device for Nanofibers  
[![Electrospinning](https://img.shields.io/badge/Application-Biomedical%2FSensors-green)](https://en.wikipedia.org/wiki/Electrospinning)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)



![Prototype](https://via.placeholder.com/800x400?text=Electrospinning+Device+Prototype) *Replace with actual image*

## 📌 Overview
A **low-cost electrospinning device** for generating nanofibers (100–500 nm) using accessible components. Electrospinning uses high voltage to transform polymer solutions into micro/nanofibers for:
- Wound dressings 🩹 
- Tissue engineering scaffolds
- Sensor membranes 📡
- Air/water filtration 🌀

**Key Innovations**:
- ✅ **80% cost reduction** vs commercial systems (~$200 material cost)
- 📱 **Bluetooth-controlled** X-Y-Z axis movement
- ⚙️ **Modular design** with open-source control
- 🧪 Validated with PVDF-HFP polymer solutions

## 🔧 Hardware Components
| Component                 | Specifications                              | Role                                  |
|---------------------------|---------------------------------------------|---------------------------------------|
| High Voltage Supply       | 4-8kV DC, 40mA                             | Creates electrostatic field           |
| Arduino Uno               | ATmega328P, 14 digital I/O                 | Central controller                    |
| HC-05 Bluetooth Module    | 2.4GHz, UART interface                     | Wireless control                      |
| A4988 Stepper Drivers (×5)| 2A/phase, micro-stepping                   | Motor control                         |
| NEMA 17 Stepper Motors    | 1.8° step, 12V, 200 steps/rev              | Syringe pump & XYZ movement           |
| Syringe Pump              | Custom acrylic, 5mL syringe, 0.55mm needle | Precise polymer delivery              |
| Collector Plate           | Aluminum sheet                             | Nanofiber collection                  |

## 💻 Software
- **Arduino IDE** (C/C++):
  - Flow rate control: `Q = V × A` (syringe diameter: 10mm)
  - Bluetooth command processing
- **Android Control App**:
  - Motor speed adjustment
  - XYZ-axis positioning
  - Emergency stop

[Sample Arduino Code](/code/motor_control.ino)

## ⚙️ System Workflow
```mermaid
graph TD
    A[Polymer Solution] --> B(Syringe Pump)
    B --> C[Needle Tip]
    C -- High Voltage --> D[Taylor Cone Formation]
    D --> E[Nanofiber Jet]
    E --> F[Collector Plate]
    G[Bluetooth App] --> H(Arduino)
    H --> I[Stepper Motors]
    I --> B
    I --> J[XYZ Movement]
