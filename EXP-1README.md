# Linear-Intigrated-circuits-lab-4NI23EC065
This repository contains experiments for the Linear Integrated Circuits (LIC) Lab in 4th-semester ECE. It covers op-amp applications, filters, oscillators, timers, voltage regulators, and comparators. Includes circuit simulations, datasheets, and lab manuals to help understand LIC design, analysis, and real-world applications.
## EXPERIMENT-1 180nM NMOS Amplifier Characterization using SPICE Simulation
### 1.INTRODUCTION
Metal-Oxide-Semiconductor Field-Effect Transistors (MOSFETs) are electronic devices based on Metal-Oxide-Semiconductor (MOS) technology that use the field effect. A 180nm CMOS process refers to a specific level of MOSFET semiconductor manufacturing. This technology offers advantages such as lower power requirements and reduced chip area by using ultra-thin deposited silicon dioxide for memory
### 2.PARAMETERS OF CMOS FROM DATASHEET

| Parameter                  | Value                    | Notes                                                                    |
| -------------------------- | ------------------------ | ------------------------------------------------------------------------ |
| **[Supply Voltage (Vdd)](pplx://action/followup)**   | 1.8 V                    | Recommended operating voltage.                                         |
| **[Threshold Voltage (Vth)](pplx://action/followup)** | 0.4 - 0.6 V              | Important for switching behavior.                                       |
| **[Gate Oxide Thickness](pplx://action/followup)**   | ~4e-9 m                  | Affects gate capacitance and breakdown voltage.                           |
| **[Electron Mobility (μn)](pplx://action/followup)** | ~0.045 m²/V·s          | Influences drive current.                                                |
| **[Transconductance (gm)](pplx://action/followup)**  | Depends on bias S       | Measure of the transistor's amplification ability.                      |
| **[On-Resistance (Ron)](pplx://action/followup)**    | Depends on size Ω        | Resistance when the transistor is fully on.                              |
| **[Gate Capacitance (Cg)](pplx://action/followup)**  | Depends on size F        | Affects switching speed.                                                 |
| **[Operating Temperature](pplx://action/followup)**  | 233 to 398 K             | Range of ambient temperatures the device can reliably operate in.         |
| **[Leakage Current (Ioff)](pplx://action/followup)** | <10e-12 A                | Current flowing when the transistor is off.                             |
| **[Channel Length](pplx://action/followup)**         | 180e-9 m                 | Related to the size of the transistor                                    |
### 3. COMMAN SOURCE AMPLIFIER using CMOS 180nM TECH
The Common Source (CS) amplifier is a fundamental amplifier configuration in CMOS analog circuit design, often utilized for its voltage amplification capabilities. Implemented using a Metal-Oxide-Semiconductor Field-Effect Transistor (MOSFET) in CMOS technology, the CS amplifier provides a moderate voltage gain, high input impedance, and moderate output impedance. In this configuration, the input signal is applied to the gate of the MOSFET, and the output signal is taken from the drain. The performance of a CS amplifier is highly dependent on the biasing conditions, transistor parameters, and load impedance, making it a crucial circuit for understanding MOSFET behavior and amplifier design principles.
#### CIRCUIT DIAGRAM
<img src="https://github.com/user-attachments/assets/93230bc0-0532-408f-a659-c1b7883a1c13" width="300" height="300">
