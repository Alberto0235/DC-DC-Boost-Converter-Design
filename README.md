# ⚡ DC-DC Boost Converter Design

## Project Overview
This repository contains the complete documentation, **LTspice simulation files**, and analysis for a **DC-DC Boost Converter** project. Developed for a Power Electronics Laboratory course, the work focuses on the full design cycle: theoretical sizing, performance simulation, and **practical realization** on a breadboard.

The core objective was to regulate an input voltage ($V_{in}=5 \, \si{\volt}$) to a stable output voltage ($V_{o}=10 \, \si{\volt}$) across a dynamic load range, with a specific focus on:
* Achieving **acceptable efficiency** under varying loads.
* Mitigating switching noise and transients using a custom-designed **RC Snubber** circuit.

The official laboratory report detailing all calculations and results can be found below:
➡️ **[Download Final Laboratory Report (EN)](Boost_Converter_Project_Report.pdf)**

---

## 🛠️ Practical Implementation and Setup
The circuit was built and tested to validate the theoretical model and to analyze non-idealities introduced by the breadboard and component parasitics.

### Instrumentation Used
Accurate measurement and signal generation were ensured using the following equipment:


*The full laboratory setup, including the Oscilloscope, Function Generator, Bench Power Supply, and Electronic Load.*

### Circuit Assembly and Probing
The final circuit was assembled on a breadboard, paying close attention to component proximity to minimize parasitic inductance. Note the specialized probing technique used on the sensitive switching node to reduce measurement-induced interference.



[Image of the circuit on breadboard]

*The final boost converter circuit assembled on the breadboard.*

---

## 📊 Key Operational Results
The analysis focused on measuring efficiency ($E_{ff}$) as a function of output current ($I_{out}$) and verifying signal integrity.

### 1. Efficiency vs. Output Current
Efficiency analysis showed a peak at moderate load ($0.2 \, \si{\ampere}$), confirming that conduction and switching losses dominate at higher output currents ($0.9 \, \si{\ampere}$).

**** *Relationship between converter efficiency and output current, derived from experimental data.*

### 2. Signal Integrity and Snubber Efficacy
The oscilloscope capture below illustrates the key signals used for analysis. Measurements confirmed the successful operation in **Continuous Conduction Mode (CCM)** and highlighted the impact of non-ideal components (diode drop, ESR).


*Oscilloscope signals: Output Voltage ($V_o$), Switching Node, Input Voltage ($V_{in}$), and MOSFET Gate Drive (Duty Cycle).*

---

## 💻 Simulation Files (LTspice)
The LTspice files allow for the full reproduction of the design and snubber analysis.

| File | Description |
| :--- | :--- |
| [`simulations/boostconverter.asc`](simulations/boostconverter.asc) | Schematic of the nominal Boost Converter circuit used for component sizing and CCM verification. |
| [`simulations/boostconverterwithsnapper.asc`](simulations/boostconverterwithsnapper.asc) | Schematic including the designed **RC Snubber** (optimized for $R_{SNB}=16\Omega$, $C_{SNB}=0.66nF$) for transient reduction. |
| `simulations/components/` | Contains the custom library files (`.lib`, `.txt`) required to correctly model non-ideal components (e.g., MBR760 Diode). |

---

## 📜 License
This project is licensed under the **MIT License**.
