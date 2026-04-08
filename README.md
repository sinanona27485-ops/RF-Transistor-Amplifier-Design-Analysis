# RF Transistor Amplifier: Design, Stability, and Matching

This repository showcases the complete design cycle of an RF Transistor Amplifier optimized for the **450 MHz** band. The project focuses on the critical balance between gain, port matching, and unconditional stability using **Ansoft Designer**.

## Technical Summary

  * [cite_start]**Operating Frequency:** 450 MHz[cite: 107, 109].
  * [cite_start]**Architecture:** BJT/FET Discrete Amplifier with Lumped Element Matching[cite: 1, 284].
  * [cite_start]**Stability Correction:** Parallel Resistor Shunt Method[cite: 114].
  * [cite_start]**Optimization:** Simultaneous $S_{11}$ and $S_{22}$ tuning[cite: 239, 286].

-----

## DC Bias & Schematic Design

The circuit utilizes a voltage-divider bias configuration to establish a stable operating point ($I_C, V_{CE}$).

  * [cite_start]**Supply Voltage:** 12V DC[cite: 8, 300].
  * [cite_start]**Biasing Network:** 62k$\Omega$ and 620$\Omega$ resistors provide the necessary base/gate current[cite: 11, 293, 298].
  * [cite_start]**RF Isolation:** A 1000nH RF Choke (RFC) is used to prevent RF leakage into the DC supply[cite: 12, 295].
  * [cite_start]**DC Blocking:** 1nF capacitors at input and output ports ensure that DC bias does not affect the source or load[cite: 20, 21, 305].

[cite_start]*Figure 1: Complete RF Amplifier Schematic[cite: 1, 5].*

-----

## Stability Analysis & Stabilization

A primary focus of this design was ensuring **unconditional stability** ($K > 1$).

### Parallel Resistor Stabilization

[cite_start]To move the stability circles out of the Smith Chart's active region, a **parallel resistor** was implemented before the output[cite: 114].

  * [cite_start]**Methodology:** The red output stability circle was monitored at 450 MHz[cite: 115].
  * [cite_start]**Calculation:** The resistance value was determined by finding where the circle is most parallel to the constant Conductance ($G$) circles[cite: 115].
  * [cite_start]**Formula:** $$R_{parallel} = \frac{1}{Y/50}$$ [cite: 116]

[cite_start]*Figure 2: Output Stability Circles at 450 MHz[cite: 44, 61].*

-----

## Impedance Matching & S-Parameters

[cite_start]Post-stabilization, the input and output networks were matched to a 50$\Omega$ system[cite: 1, 25].

### Simulation Results

  * [cite_start]**$S_{11}$ (Input Matching):** Achieved a return loss of approximately -50 dB at the center frequency[cite: 217].
  * [cite_start]**$S_{22}$ (Output Matching):** Tuned to match the input, ensuring maximum power transfer[cite: 243, 246].
  * [cite_start]**Design Insight:** For the output port, a **1nF series capacitor** was placed between the parallel inductor and ground[cite: 285]. [cite_start]This blocks the DC path to ground while allowing for precise RF impedance matching[cite: 285].

[cite_start]*Figure 3: Optimized $S_{11}$ and $S_{22}$ after simultaneous tuning[cite: 239, 246].*

-----

## Repository Contents

  * `/Project_Files`: Ansoft Designer (Nexxim) project files.
  * `/Results`: High-resolution S-parameter plots and stability circles.
  * `/Documentation`: Detailed design report and calculation steps.

-----

## 👨‍💻 Author

**Sinan ONA**
*3rd-year Electrical and Electronics Engineering Student*
[LinkedIn](https://www.google.com/search?q=https://www.linkedin.com/in/sinan-ona-083897360) | [GitHub](https://www.google.com/search?q=https://github.com/sinanona27485-ops)
