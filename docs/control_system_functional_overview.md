# IX-Shimizu Control System Functional Overview

**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License  

---

## Purpose

This document provides a non-code overview of how IX-Shimizu’s control logic functions under real-world deployment conditions. It complements `/src/control_logic/plc_program_flow.txt`.

---

## 1. Primary Control System Roles

- **Monitor Environmental Inputs:**
  - Oil PPM Sensor
  - Turbidity Sensor
  - Flow Rate Sensors
  - Battery SOC Monitor

- **Activate Capture and Filtration Systems:**
  - Nanoparticle Dosing
  - Sponge Compression
  - Regeneration Cycles

- **Manage Power System:**
  - Ambient Energy Source Prioritization
  - Battery SOC Protection

- **Handle Safety and Shutdown Events:**
  - Trigger failsafe states
  - Log critical events

---

## 2. Control System State Flow

| State Name        | Description                           |
|-------------------|--------------------------------------|
| Idle Mode         | No oil detected, system in low-power |
| Capture Mode      | Oil detected, nanoparticle dosing + sponge system active |
| Regeneration Mode | Triggered by turbidity level or capture cycle count |
| Safe Mode         | Low battery or sensor fault state    |

---

## 3. Input/Output Overview

- **Inputs:**
  - Sensor Array Data (Oil PPM, Turbidity, Flow Rate)
  - Battery Management System (BMS) Data
  - Operator Commands (if telemetry/control channel is active)

- **Outputs:**
  - Dosing Pump Activation
  - Sponge Compression Motor Control
  - Magnetic Array Field Activation
  - Data Log Events
  - Telemetry Transmission

---

## 4. Real-Time Operating Profile

- **Main Control Loop Cycle Time:** 1–5 seconds
- **Emergency Event Response Time:** < 1 second
- **Telemetry Sync Interval:** Every 60 seconds by default

---

## 5. Configuration Management

- All key parameters are adjustable via:
  - `/src/config/system_constants.py`
  - Hardware DIP switches (for deployment condition overrides)

---

## 6. System Diagnostics

- Built-in self-test (BIST) runs on startup
- Sensor validation loop checks every 60 seconds
- Failsafe triggers if:
  - Data timeout from any sensor exceeds 120 seconds
  - Battery voltage anomaly detected
  - Oil PPM sensor reports invalid range values

---

## End of IX-Shimizu Control System Functional Overview
