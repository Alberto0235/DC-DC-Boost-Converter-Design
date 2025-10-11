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










# ⚡ DC-DC Boost Converter: Design, Simulation, and Implementation

**Course:** Power Electronics Laboratory
**University:** Alma Mater Studiorum – University of Bologna (Cesena Campus)
**Academic Year:** 2023/2024

---

## 📌 Project Overview
This repository hosts the complete documentation and source files for a **DC-DC Boost Converter** project. The work covers the full development cycle: from theoretical sizing and **LTspice simulation** to practical realization and operational analysis on a breadboard.

The primary objective was the regulation and stability of the output voltage ($V_{o}$), alongside optimizing the circuit's performance for efficiency and mitigating switching noise through a custom-designed **RC Snubber**.

### Design Specifications
| Parameter | Value | Note |
| :--- | :--- | :--- |
| Input Voltage ($V_{in}$) | $5 \, \si{\volt}$ | Base supply voltage. |
| Nominal Output Voltage ($V_o$) | $10 \, \si{\volt}$ | Achieved via Duty Cycle regulation. |
| Switching Frequency ($f_{sw}$) | $25 \, \si{\kilo\hertz}$ | Operating frequency in CCM. |
| Inductance ($L$) | $150 \, \si{\micro\henry}$ | Calculated to ensure Continuous Conduction Mode (CCM). |

The official technical report detailing all calculations, measurements, and analysis can be downloaded here:
➡️ **[Download Final Laboratory Report (EN)](Boost_Converter_Project_Report.pdf)**

---

## 🛠️ Tools and Software Used

### Laboratory Instrumentation
The following professional equipment was used for practical realization and dynamic characterization:

![Laboratory equipment setup (oscilloscope, function generator, power supply).](images/Equipment.jpg)

* **Bench Power Supply:** Provides stable $V_{in}$.
* **Function Generator:** Generates the square wave for MOSFET gate drive.
* **Electronic Load:** Simulates variable load conditions for efficiency analysis.
* **Digital Oscilloscope:** Monitors signals, output ripple, and switching node transients.

### Software
* **LTspice XVII:** Used for component sizing, CCM verification, and snubber circuit simulation.
* **LaTeX / Siunitx:** Used for professional technical report generation.

---

## 📊 Key Operational Results

### Circuit Assembly and Probing
The final circuit was assembled on a breadboard. Specialized probing techniques (e.g., using a spring tip on the oscilloscope probe) were employed on the sensitive switching node to minimize parasitic inductance and ensure accurate measurements.

![Final DC-DC Boost Converter circuit assembled on the breadboard.](images/Circuit on breadboard.jpg)

### Efficiency Analysis ($E_{ff}$)
Experimental data confirmed the performance goals, showing a clear dependency of efficiency on the output current:

* **Peak Efficiency:** Recorded at moderate load ($I_{out} = 0.2 \, \si{\ampere}$).
* **Losses:** Efficiency decreases at high output currents due to increased switching and conduction losses (dominated by component resistances and breadboard parasitics).

![Graph showing efficiency versus output current (Eff-Io curve).](images/Eff-Io.png)
*Efficiency vs. Output Current: Experimental data highlighting the peak efficiency of the converter.*

### Signal Integrity and Snubber Efficacy
The analysis confirmed stable operation and demonstrated the effectiveness of the RC snubber ($R_{SNB}=16 \, \si{\ohm}$, $C_{SNB}=0.66 \, \si{\nano\farad}$) in reducing unwanted transients (ringing).

![Oscilloscope capture showing input, output, and switching node signals.](images/Signals zoom out.jpg)
*Visual representation of signals acquired: Output Voltage ($V_o$), Switching Node, Input Voltage ($V_{in}$), and MOSFET Gate Drive (Duty Cycle).*

---

## 💻 Simulation Files (LTspice)
The LTspice files allow for the full reproduction of the design and performance analysis.

| File | Description |
| :--- | :--- |
| [`simulations/boostconverter.asc`](simulations/boostconverter.asc) | Schematic of the nominal Boost Converter circuit (without snubber). |
| [`simulations/boostconverterwithsnapper.asc`](simulations/boostconverterwithsnapper.asc) | Schematic of the circuit with the optimized **RC Snubber** implemented for transient reduction. |
| `simulations/components/` | Contains the custom library files (`.lib`, `.txt`) required to correctly model non-ideal components (e.g., MBR760 Diode). |

---

## 📜 License
The source code and simulation files are released under the **MIT License**. The report and documentation are released under the **CC BY 4.0** (Creative Commons Attribution 4.0 International) License.
