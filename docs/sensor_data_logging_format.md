# IX-Shimizu Sensor Data Logging Format

**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License  

---

## Purpose

This document defines the standardized file structure and schema for sensor data logging in IX-Shimizu deployments.

---

## 1. Log File Format

- **File Type:** CSV or JSONL (JSON Lines)
- **Retention Policy:** 30 days minimum, auto-archive beyond 30 days
- **Storage Location:** Internal solid-state storage or external telemetry uplink

---

## 2. CSV Schema Example

### CSV Header Row:
```csv
timestamp, oil_ppm, turbidity_ntu, flow_rate_lpm, battery_soc_percent, nanoparticle_dose_mg, sponge_regen_cycle

CSV Data Row Example: 2025-07-15T14:00:00Z, 4.5, 7, 25.0, 78, 35, 3

3. JSONL Schema Example
{
  "timestamp": "2025-07-15T14:00:00Z",
  "oil_ppm": 4.5,
  "turbidity_ntu": 7,
  "flow_rate_lpm": 25.0,
  "battery_soc_percent": 78,
  "nanoparticle_dose_mg": 35,
  "sponge_regen_cycle": 3
}

4. Field Definitions
Field Name	Data Type	Description
timestamp	ISO 8601	UTC Time of Measurement
oil_ppm	Float	Oil Concentration (ppm)
turbidity_ntu	Integer	Turbidity (NTU)
flow_rate_lpm	Float	Liters Per Minute Flow Rate
battery_soc_percent	Integer	State of Charge %
nanoparticle_dose_mg	Integer	Nanoparticle Quantity Dosed (mg)
sponge_regen_cycle	Integer	Number of Sponge Regeneration Cycles Completed

6. System Configuration Reference
Logging intervals and formats can be configured via /src/config/system_constants.py.


