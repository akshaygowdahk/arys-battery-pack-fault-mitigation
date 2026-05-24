# arys-battery-pack-fault-mitigation

**Arys Garage Assignment – Q3 | Section A: Electronics / Embedded / EEE**

**Candidate:** Akshay Gowda HK  
**USN:** 1BM22EE007  
**Assignment:** 10s10p Battery Pack Fault & Mitigation (21700 NMC)

---

## Project Scope

This project simulates a **10 series × 10 parallel (10s10p)** lithium-ion battery pack using Molicel **INR-21700-P45B** cells in MATLAB Simulink (Simscape Battery). The simulation covers:

- Normal discharge characterisation
- Single-cell fault injection via internal resistance increase
- Thermal runaway behaviour modelling
- Electrical mitigation system design and re-simulation
- Before vs. after comparison of SOC, SOH, Voltage, Current, and Temperature

---

## Cell Specifications

| Parameter | Value |
|---|---|
| Cell model | Molicel INR-21700-P45B |
| Nominal capacity | 4.5 Ah |
| Pack configuration | 10s10p |
| Pack nominal voltage | ~36V |
| Pack total capacity | ~45 Ah |
| Pack total energy | ~1.62 kWh |
| Max continuous discharge | 450A |

---

## Repository Structure

```
arys-battery-pack-fault-mitigation/
│
├── simulation/
│   ├── normal_discharge/       # Baseline discharge simulation files (.slx, .m)
│   ├── fault_injection/        # Fault scenario: increased internal resistance in one cell
│   └── mitigation/             # Re-simulation with fuse, MOSFET, bypass, current limiter
│
├── results/
│   ├── plots/                  # SOC, SOH, Voltage, Current, Temperature plots (PNG/PDF)
│   └── logs/                   # Simulation data logs (.mat, .csv)
│
├── docs/
│   ├── report.pdf              # Final submission report
│   └── block_diagrams/         # Simulink screenshots and architecture diagrams
│
└── README.md
```

---

## Simulation Overview

### 1. Normal Discharge
- Simulated using Simscape Battery `arysbattery` block (Battery Builder, lumped model)
- Discharge via controlled current source
- SOC, terminal voltage, current, and cell temperature recorded
- SOH estimated via internal resistance tracking (`SOH_estimator` subsystem)

### 2. Fault Injection
- Internal resistance of one cell increased (stepped via pulse-controlled resistor)
- Thermal runaway behaviour triggered when pack temperature exceeds threshold
- Fault detection logic: voltage comparator (`> 330`) monitors pack voltage drop

### 3. Mitigation System
Electrical mitigation circuit includes:
- **Fuse** – overcurrent protection
- **MOSFET disconnect** – isolates faulty cell/module on fault detection
- **Bypass path** – maintains pack operation with reduced capacity
- **Current limiter** – caps discharge current post-fault

### 4. Comparison (Before vs. After Mitigation)
Results compared across:
- State of Charge (SOC)
- State of Health (SOH)
- Pack Voltage
- Current
- Temperature

---

## Tools Used

| Tool | Purpose |
|---|---|
| MATLAB R2025a (v25.2) | Simulation environment |
| Simscape Battery v25.2 | Battery Builder & cell modelling |
| Simulink | System-level block diagram |
| Claude (Anthropic) | Documentation, analysis, debugging support |

---

## AI Usage

**Tool:** Claude (Anthropic) – claude.ai  
**How it helped:**
- Cell parameter validation against Molicel P45B datasheet
- SOH estimator logic review
- Mitigation circuit architecture suggestions
- Report structure and documentation

**Prompts used:** Available in `docs/ai_usage_log.md`

---

## How to Run

1. Open MATLAB R2025a
2. Navigate to `simulation/normal_discharge/` and open the `.slx` file
3. Run simulation — scopes will display SOC, voltage, current, and temperature
4. For fault scenario, open `simulation/fault_injection/` model and run
5. For mitigation, open `simulation/mitigation/` model and run
6. Export results to `results/plots/` and `results/logs/`

---

## Submission

- **Email:** future@arysgarage.com  
- **Subject:** Assignment Submission – Akshay Gowda HK – 10s10p Battery Pack Fault & Mitigation (21700 NMC)
- **Deadline:** 7th December 2025, 6:00 PM IST
