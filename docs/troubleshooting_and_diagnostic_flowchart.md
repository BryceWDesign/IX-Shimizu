# IX-Shimizu Troubleshooting and Diagnostic Flowchart

**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License  

---

## Purpose

This document provides a text-based flowchart for diagnosing common IX-Shimizu system issues without requiring additional visual aids. This adheres to the no-CAD/no-image structure required.

---

## 1. Diagnostic Flowchart (Text-Structured)

---

**START**

→ Is the system powered on?  
    → YES → Continue  
    → NO → Check battery charge → Check power switch → If unresolved: Check main circuit breaker

---

→ Is the control panel responsive?  
    → YES → Continue  
    → NO → Check PLC connections → Check sensor bus wiring → If unresolved: Replace PLC unit

---

→ Are oil PPM readings within expected range?  
    → YES → System functioning normally  
    → NO → Continue troubleshooting:

    → Are oil PPM readings stuck at zero?  
        → YES → Clean oil sensor → Recalibrate → If unresolved: Replace oil sensor module  
        → NO → Continue

    → Are oil PPM readings fluctuating wildly?  
        → YES → Check water flow stability → Inspect nanoparticle dosing system for blockage → Recalibrate sensors

---

→ Is battery SOC above 20%?  
    → YES → Continue  
    → NO → Switch to safe mode → Recharge system batteries manually

---

→ Are telemetry or data logs available?  
    → YES → Review logs for deeper fault analysis  
    → NO → Inspect communication module → Check antenna integrity → Replace as needed

---

**END: If all checks pass but system still malfunctions → Retrieve unit for full lab diagnosis**

---

## 2. Notes for Field Operators

- All major fault codes are displayed via status LEDs and logs within `/logs/` directory.
- If a unit experiences repeat failures in the same subsystem, escalate to full system recovery protocol.
- For replacement part numbers and sourcing, refer to `/docs/system_bom.md`.

---

## End of IX-Shimizu Troubleshooting and Diagnostic Flowchart
