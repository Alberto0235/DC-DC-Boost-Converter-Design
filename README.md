
---

# ⚡ DC-DC Boost Converter: Design, Simulation, and Implementation

**Course:** Power Electronics Laboratory  
**University:** University of Bologna, Cesena Campus 
**Academic Year:** 2023/2024  

---

## 📌 Project Overview

This repository contains the complete documentation, **LTspice simulation files**, and analysis for a **DC-DC Boost Converter** project. The work covers the full development cycle: from **theoretical sizing** to **simulation** and **practical implementation** on a breadboard.

**Project Objectives**

1.  Regulate an input voltage of **$V_{in} = 5 V$** to a stable output voltage of **$V_{o} = 10 V$**.
2.  Optimize efficiency across a dynamic load range.
3.  Minimize switching noise and transients via a custom-designed **RC Snubber**.

**Design Specifications:**

| Parameter                            | Value         | Notes                                                   |
| :----------------------------------- | :------------ | :------------------------------------------------------ |
| **Input Voltage** ($V_{in}$)         | $5 V$         | Base supply voltage                                     |
| **Output Voltage** ($V_{o}$)         | $10 V$        | Target voltage regulated via duty cycle                 |
| **Switching Frequency** ($f_{sw}$)   | $25 kHz$      | Operating frequency in Continuous Conduction Mode (CCM) |
| **Inductance** ($L$)                 | $150 \ \mu H$ | Ensures CCM                                             |
| **Output Current Range** ($I_{out}$) | $0 A - 0.9 A$ | Dynamic load conditions                                 |

The full laboratory report with calculations and analysis can be found here:
➡️ **[Download Boost Converter Project Report (EN)](Boost_Converter_Project_Report.pdf)**

---

## 🛠️ Tools and Software Used

### Laboratory Instrumentation

The following professional instruments were employed for circuit testing and characterization:

![Tools Placeholder](https://via.placeholder.com/600x300?text=Laboratory+Instruments)
*Example: Oscilloscope, Function Generator, Bench Power Supply, Electronic Load*

* **Bench Power Supply:** Provides stable input voltage.
* **Function Generator:** Generates MOSFET gate drive signals.
* **Electronic Load:** Allows efficiency analysis under variable loads.
* **Digital Oscilloscope:** Monitors output ripple, switching node transients, and signal integrity.

### Software

* **LTspice XVII:** For component sizing, simulation, and snubber analysis.
* **LaTeX / Siunitx:** For professional technical report preparation.

---

## 📊 Key Operational Results

### Circuit Assembly and Probing

The final circuit was assembled on a breadboard. Special attention was given to **probe placement** and minimizing parasitic inductances on the switching node.

### Efficiency Analysis

Efficiency (E_\mathrm{ff}) was measured across the output current range. Results:

* **Peak Efficiency:** (E_\mathrm{ff} \approx 87%) at (I_\mathrm{out} = \SI{0.2}{\ampere})
* **Efficiency Drop:** Observed at high loads ((I_\mathrm{out} \approx \SI{0.9}{\ampere})) due to conduction and switching losses.

![Efficiency vs Output Current Placeholder](https://via.placeholder.com/600x400?text=Efficiency+vs+Iout)

### Signal Integrity and RC Snubber Efficacy

The RC Snubber ((R_\mathrm{SNB} = \SI{16}{\ohm}, C_\mathrm{SNB} = \SI{0.66}{\nano\farad})) effectively reduced ringing on the switching node.

![Oscilloscope Capture Placeholder](https://via.placeholder.com/600x400?text=Oscilloscope+Signals)

Signals measured: Input voltage (V_\mathrm{in}), Output voltage (V_\mathrm{o}), Switching node voltage, MOSFET gate drive.

---

## 🗂️ Repository Structure

```
Boost-Converter-Project/
│
├─ Boost_Converter_Project_Report.pdf   # Final technical report
├─ LICENSE                             # MIT License
├─ README.md                           # This file
├─ simulations/
│   ├─ boostconverter.asc              # Nominal Boost Converter schematic
│   ├─ boostconverterwithsnapper.asc   # Boost Converter with RC Snubber
│   └─ components/
│       ├─ diode.lib
│       ├─ mosfet.lib
│       └─ passive_components.txt
```

* `boostconverter.asc` → Base circuit for sizing and CCM verification
* `boostconverterwithsnapper.asc` → Includes RC Snubber for transient suppression
* `components/` → Custom library files for non-ideal component modeling

---

## 📜 License

* **Source Code and Simulation Files:** MIT License
* **Technical Report and Documentation:** CC BY 4.0 (Creative Commons Attribution 4.0 International)

---
