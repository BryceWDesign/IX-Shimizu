# IX-Shimizu Deployment Checklist

**Project:** IX-Shimizu  
**Author:** Bryce Wooster  
**License:** Apache License 2.0 + Custom Legal License

---

## Deployment Phase 1 — Pre-Installation Checklist

- [ ] Verify all components have been sourced:
  - Nanoparticle materials
  - Magnetic capture array
  - PDMS sponge modules
  - Ambient energy harvesting modules (Solar, Wave, Thermal)
  - LiFePO₄ battery bank and BMS
  - Sensors: Oil PPM, Turbidity, Flow Rate, SOC

- [ ] Confirm marine environmental compliance documentation filed
- [ ] Validate system constants (`/src/config/system_constants.py`) against local conditions

---

## Deployment Phase 2 — Hardware Installation

- [ ] Assemble floating or submersible housing per IX-Shimizu specs
- [ ] Install sponge filtration stack securely
- [ ] Mount magnetic capture array with verified polarity configuration
- [ ] Connect battery systems and ambient energy modules
- [ ] Install sensor suite and verify calibration baseline

---

## Deployment Phase 3 — System Software Setup

- [ ] Flash control logic onto PLC or embedded system
- [ ] Upload system constants and calibration files
- [ ] Verify `/src/utils/` sensor scripts function with live hardware
- [ ] Test telemetry or data logging connection (if equipped)

---

## Deployment Phase 4 — Pre-Activation Validation

- [ ] Run Power On Self-Test (POST) sequence
- [ ] Verify oil PPM readings with clean water baseline
- [ ] Simulate oil-contaminated water sample and check nanoparticle dosing response
- [ ] Trigger manual sponge regeneration cycle to confirm mechanical response
- [ ] Confirm all safety shutdown triggers function:
  - SOC below minimum threshold
  - Oil PPM over shutdown threshold
  - Sensor malfunction simulation

---

## Deployment Phase 5 — Activation & Monitoring

- [ ] Activate IX-Shimizu system in target environment
- [ ] Monitor initial 24-hour operational performance
- [ ] Record oil removal efficiency statistics
- [ ] Log ambient energy system performance
- [ ] Schedule routine maintenance per `/docs/maintenance_and_regeneration.md`

---

## Deployment Phase 6 — Ongoing Maintenance

- [ ] Monthly sensor calibration
- [ ] Nanoparticle batch regeneration every 10 cycles
- [ ] Sponge stack replacement every 50 cycles
- [ ] Bi-annual battery system inspection

---

## End of IX-Shimizu Deployment Checklist
