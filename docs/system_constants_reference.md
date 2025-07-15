# IX-Shimizu System Constants Reference

**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License  

---

## Purpose

This document provides clear definitions and recommended baseline values for all configurable constants in the IX-Shimizu system. It directly correlates with `/src/config/system_constants.py`.

---

## 1. Oil PPM Thresholds

| Constant Name             | Default Value | Description                          |
|--------------------------|---------------|--------------------------------------|
| `OIL_PPM_ALERT_LEVEL`    | 5.0 ppm       | Trigger warning system               |
| `OIL_PPM_MAX_LEVEL`      | 10.0 ppm      | Activate emergency shutdown/capture  |
| `OIL_PPM_ZERO_OFFSET`    | 0.1 ppm       | Baseline drift correction            |

---

## 2. Turbidity Thresholds

| Constant Name             | Default Value | Description                          |
|--------------------------|---------------|--------------------------------------|
| `TURBIDITY_ALERT_LEVEL`  | 8 NTU         | Trigger sponge regeneration alert    |
| `TURBIDITY_MAX_LEVEL`    | 20 NTU        | Force mechanical purge cycle         |

---

## 3. Flow Rate Limits

| Constant Name             | Default Value | Description                          |
|--------------------------|---------------|--------------------------------------|
| `FLOW_RATE_MIN_LPM`      | 5.0 L/min     | Minimum operational flow             |
| `FLOW_RATE_MAX_LPM`      | 30.0 L/min    | Maximum allowed flow to avoid damage |

---

## 4. Battery SOC Settings

| Constant Name                | Default Value | Description                           |
|-----------------------------|---------------|---------------------------------------|
| `BATTERY_SOC_CRITICAL_LEVEL` | 20%           | Force shutdown                        |
| `BATTERY_SOC_WARNING_LEVEL`  | 35%           | Trigger ambient power priority shift  |

---

## 5. Magnetic Field Strength Reference

| Constant Name             | Default Value | Description                          |
|--------------------------|---------------|--------------------------------------|
| `MAGNETIC_FIELD_STRENGTH` | 1.4 Tesla     | Target Gauss value for nanoparticle capture array |

---

## 6. Regeneration Timings

| Constant Name                     | Default Value | Description                          |
|----------------------------------|---------------|--------------------------------------|
| `SPONGE_REGENERATION_INTERVAL`   | 4 hours       | Time between auto sponge cycles      |
| `NANO_REGENERATION_INTERVAL`     | 10 capture cycles | Centrifuge nanoparticle cleaning frequency |

---

## Modification Notes

- All constants must be adjusted cautiously via `/src/config/system_constants.py`.
- Changes should reflect local environmental and deployment conditions.
- System software must be rebooted after changes to apply new values.

---

## End of IX-Shimizu System Constants Reference
