# IX-Shimizu System Calibration Procedures

**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License

This document provides standardized calibration procedures for IX-Shimizu sensors and core control systems.

---

## 1. Oil PPM Sensor Calibration

**Tools Required:**
- Certified calibration oil standards
- Clean seawater sample (baseline)

**Procedure:**

1. Connect oil PPM sensor to the diagnostic interface.
2. Submerge sensor in clean seawater; record baseline reading.
3. Introduce known oil concentration incrementally:
   - 0.5 ppm
   - 1.0 ppm
   - 5.0 ppm
   - 10 ppm
4. Record sensor output at each concentration.
5. Adjust sensor offset and gain controls via `/src/config/system_constants.py` until readings match standard values.
6. Save configuration and re-test full range.

---

## 2. Turbidity Sensor Calibration

**Procedure:**

1. Fill calibration chamber with clean water sample.
2. Set baseline zero reading via control software.
3. Incrementally add standard turbidity solution to target NTU levels:
   - 1 NTU
   - 5 NTU
   - 10 NTU
   - 50 NTU
4. Adjust sensor sensitivity in control system until sensor outputs align with reference measurements.

---

## 3. Flow Rate Sensor Calibration

**Procedure:**

1. Run clean water through system at controlled flow rates using precision pump.
2. Compare sensor readings against mechanical flow meter reference.
3. Adjust flow rate scale factor within `/src/config/system_constants.py`.
4. Validate linearity across full operational flow range.

---

## 4. Battery SOC Calibration

**Procedure:**

1. Fully charge system batteries to 100%.
2. Record nominal voltage at 100%.
3. Fully discharge under load down to minimum safe voltage.
4. Record nominal voltage at 0% SOC.
5. Set these voltage ranges in battery monitoring software and verify accuracy via test cycles.

---

## 5. System Control Logic Calibration

- Validate all sensor-triggered control events by simulating:
  - High oil PPM event → Ensure capture system activates
  - Low battery SOC event → Ensure shutdown or idle mode triggers
  - High turbidity event → Validate sponge regeneration timing
- Adjust control thresholds within `/src/control_logic/plc_program_flow.txt` as needed.

---

## Calibration Schedule Summary

| Sensor Type          | Calibration Frequency |
|---------------------|----------------------|
| Oil PPM Sensor      | Monthly              |
| Turbidity Sensor    | Monthly              |
| Flow Rate Sensor    | Quarterly            |
| Battery SOC System  | Quarterly            |

---

## End of IX-Shimizu System Calibration Procedures
