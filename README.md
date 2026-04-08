# RF Transistor Amplifier: Design, Stability, and Matching

[cite_start]This repository showcases the complete design cycle of an RF Transistor Amplifier optimized for the **450 MHz** band[cite: 107, 109]. [cite_start]The project focuses on the critical balance between gain, port matching, and unconditional stability using **Ansoft Designer**[cite: 60, 61].

## Technical Summary

* [cite_start]**Operating Frequency:** 450 MHz[cite: 107, 195].
* [cite_start]**Architecture:** BJT/FET Discrete Amplifier with Lumped Element Matching[cite: 1, 284].
* [cite_start]**Stability Correction:** Parallel Resistor Shunt Method[cite: 114].
* [cite_start]**Optimization:** Simultaneous $S_{11}$ and $S_{22}$ tuning[cite: 239, 286].

---

## DC Bias & Schematic Design

The circuit utilizes a voltage-divider bias configuration to establish a stable operating point ($I_C, V_{CE}$).

* [cite_start]**Supply Voltage:** 12V DC[cite: 8, 300].
* [cite_start]**Biasing Network:** 62k$\Omega$ and 620$\Omega$ resistors provide the necessary base/gate current[cite: 11, 293, 298].
* [cite_start]**RF Isolation:** A 1000nH RF Choke (RFC) is used to prevent RF leakage into the DC supply[cite: 12, 295].
* [cite_start]**DC Blocking:** 1nF capacitors at input and output ports ensure that DC bias does not affect the source or load[cite: 20, 21, 305].

### Initial Design Phase
[**Start Circuit.pdf**](./Results/Start%20Circuit.pdf)
[cite_start]*Figure 1: Initial RF Amplifier Schematic before stabilization and matching[cite: 1].*

---

## Stability Analysis & Stabilization

[cite_start]A primary focus of this design was ensuring **unconditional stability** ($K > 1$)[cite: 33, 108, 196].

### Parallel Resistor Stabilization

[cite_start]To move the stability circles out of the Smith Chart's active region, a **parallel resistor** was implemented before the output[cite: 114].

* [cite_start]**Methodology:** The red output stability circle was monitored at 450 MHz[cite: 46, 115].
* [cite_start]**Calculation:** The resistance value was determined by finding where the circle is most parallel to the constant Conductance ($G$) circles[cite: 115].
* [cite_start]**Formula:** $$R_{parallel} = \frac{1}{Y/50}$$ [cite: 116]

### Stability Verification
[**Stability after adding the parallel resistor at the output.pdf**](./Results/Stability%20after%20adding%20the%20parallel%20resistor%20at%20the%20output.pdf)
[cite_start]*Figure 2: Analysis of Output Stability Circles at 450 MHz after shunt resistor integration[cite: 61, 114].*

---

## Impedance Matching & S-Parameters

[cite_start]Post-stabilization, the input and output networks were matched to a 50$\Omega$ system[cite: 1, 306, 307].

### Matching Workflow
1. [cite_start][**input smith.pdf**](./Results/input%20smith.pdf) - Smith Chart derivation for input port matching[cite: 265, 266].
2. [cite_start][**output smith.pdf**](./Results/output%20smith.pdf) - Smith Chart derivation for output port matching[cite: 274, 282].

### Simulation Results

* [cite_start]**$S_{11}$ (Input Matching):** Achieved a return loss of approximately -50 dB at the center frequency[cite: 217, 225].
* **$S_{22}$ (Output Matching):** Tuned to match the input, ensuring maximum power transfer[cite: 243, 246].
* **Design Insight:** For the output port, a **1nF series capacitor** was placed between the parallel inductor and ground[cite: 285]. This blocks the DC path to ground while allowing for precise RF impedance matching[cite: 285].

### Final Performance
* [**s 11 s 22 after imp+tune.pdf**](./Results/s%2011%20s%2022%20after%20imp+tune.pdf)
* [**Final circuit.pdf**](./Results/Final%20circuit.pdf)
*Figure 3: Optimized $S_{11}$ and $S_{22}$ response and final circuit architecture[cite: 239, 284].*

---

## How to Use and Transistor Customization

* **Software:** Open the project file in **Ansoft Designer**.
* **Transistor Model:** BFR93A.
* **To change the transistor:** Users must update the component path within the Ansoft Designer properties to point to their local `.s2p` or device model file.
* **Note:** Changing the transistor will likely shift the stability and matching points, requiring a re-tuning of the parallel resistor and LC network.

---

## Repository Contents

* `/Project_Files`: Ansoft Designer (Nexxim) project files.
* `/Results`: High-resolution S-parameter plots and stability circles.
* `/Docs`: Detailed design reports and PDF circuit exports.

---

## Author

**Sinan ONA**
*3rd-year Electrical and Electronics Engineering Student*
[LinkedIn](https://www.linkedin.com/in/sinan-ona-083897360) | [GitHub](https://github.com/sinanona27485-ops)
