# IX-Shimizu Ambient Energy Power System Overview

**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License  

---

## System Goal

The IX-Shimizu system is engineered to operate independently from fossil fuel or grid-tied power systems, relying entirely on ambient energy harvesting to maintain its ≥99% oil removal performance target.

---

## Primary Ambient Energy Sources

### 1. Solar Energy Subsystem

- **Panel Type:** Marine-grade monocrystalline or bifacial panels
- **Power Range:** 300W–500W per panel
- **Mounting:** Float-surface array, adjustable tilt
- **Advantages:** High reliability, widely available
- **Considerations:** Reduced efficiency in stormy conditions or polar deployments

---

### 2. Wave Energy Subsystem

- **Mechanism Type:** Oscillating Water Column (OWC) or Point Absorber
- **Power Output:** 50–500W continuous (environment-dependent)
- **Mounting:** Integrated into float structure or as tethered auxiliary unit
- **Advantages:** Continuous generation in overcast conditions
- **Considerations:** Structural complexity, requires robust anchoring

---

### 3. Thermal Gradient Power Subsystem (Optional)

- **Type:** Stirling Engine or Thermoelectric Generator (TEG) Array
- **Temperature Delta Required:** ≥20°C for practical output
- **Advantages:** Can leverage ocean surface vs. deeper water temperature differences
- **Considerations:** Lower power density compared to solar or wave systems

---

## Power Management System (PMS)

- **Battery Bank:** LiFePO₄ preferred, 48V nominal system
- **BMS Type:** CAN Bus or RS485 Marine-Grade Controller
- **Charge Controllers:** MPPT Hybrid Solar/Wave/TEG Controllers
- **Redundancy:** Dual independent charge regulation paths

---

## Power Usage Breakdown

| Subsystem                       | Peak Power Requirement |
|---------------------------------|-----------------------|
| Nanoparticle Dosing & Capture   | 80–120W               |
| Sponge Compression System       | 150–250W              |
| Sensor Suite                    | 30–50W                |
| PLC/Control System              | 15–30W                |
| Auxiliary Communication        | 20–60W (if enabled)   |

**Average Continuous Load:** ~300–400W total

---

## System Resilience Notes

- Designed with surplus generation capacity to cover nighttime and low-sun conditions.
- Minimum operational runtime without ambient input: 48–72 hours via internal batteries.
- All components IP68+ rated for marine deployment durability.

---

## End of IX-Shimizu Power System Overview
