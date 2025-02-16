# Linear-Intigrated-circuits-lab-4NI23EC065
This repository contains experiments for the Linear Integrated Circuits (LIC) Lab in 4th-semester ECE. It covers op-amp applications, filters, oscillators, timers, voltage regulators, and comparators. Includes circuit simulations, datasheets, and lab manuals to help understand LIC design, analysis, and real-world applications.
## EXPERIMENT-1 180nM NMOS Amplifier Characterization using SPICE Simulation
### 1.INTRODUCTION
Metal-Oxide-Semiconductor Field-Effect Transistors (MOSFETs) are electronic devices based on Metal-Oxide-Semiconductor (MOS) technology that use the field effect. A 180nm CMOS process refers to a specific level of MOSFET semiconductor manufacturing. This technology offers advantages such as lower power requirements and reduced chip area by using ultra-thin deposited silicon dioxide for memory
### 2.PARAMETERS OF NMOS from tsmc018.lib:

| Parameter                  | Value                    | Notes                                                                    |
| -------------------------- | ------------------------ | ------------------------------------------------------------------------ |
| **[Supply Voltage (Vdd)](pplx://action/followup)**   | 1.8 V                    | Recommended operating voltage.                                         |
| **[Threshold Voltage (Vth)](pplx://action/followup)** | .366 V              | Important for switching behavior.                                       |
| **[Gate Oxide Thickness](pplx://action/followup)**   | 4.1 nm                  | Affects gate capacitance and breakdown voltage.                           |
| **[Electron Mobility (μn)](pplx://action/followup)** | 273.81 cm²/V·s          | Influences drive current.                                                         |
| **[Gate Capacitance (Cg)](pplx://action/followup)**  | 8.23E-10 F        | Affects switching speed.                                                 |
| **[Operating Temperature](pplx://action/followup)**  |  27 C             | Range of ambient temperatures the device can reliably operate in.         |
| **[Leakage Current (Ioff)](pplx://action/followup)** | <10e-12 A                | Current flowing when the transistor is off.                             |
| **[Channel Length](pplx://action/followup)**         | 180e-9 m                 | Related to the size of the transistor                                    |
### 3. COMMAN SOURCE AMPLIFIER using CMOS 180nM TECH
The Common Source (CS) amplifier is a fundamental amplifier configuration in CMOS analog circuit design, often utilized for its voltage amplification capabilities. Implemented using a Metal-Oxide-Semiconductor Field-Effect Transistor (MOSFET) in CMOS technology, the CS amplifier provides a moderate voltage gain, high input impedance, and moderate output impedance. In this configuration, the input signal is applied to the gate of the MOSFET, and the output signal is taken from the drain. The performance of a CS amplifier is highly dependent on the biasing conditions, transistor parameters, and load impedance, making it a crucial circuit for understanding MOSFET behavior and amplifier design principles.
#### CIRCUIT DIAGRAM
<img src="https://github.com/user-attachments/assets/93230bc0-0532-408f-a659-c1b7883a1c13" width="300" height="300"/>

### 4.DC OPERATING POINT
To find DC operating point we know that Resistor(R) has a power rating of 100 micro Watt from Eq: P=VI where P=100u and V=1.8V we can find I I=P/V=55.55µA = 5.5551 X 10-5 where I is drain current, hence I=Id now if we know Id by trial and error we can find the width and length ot the MOSFET bu keeping anyone of the parameter constant lets keep length constant say 180n meter. from trial and error we found ot that the width should be 0.2µ meter to get Id as 55.55µA. to find rest of the parameters we need to do simulation to do simulation we need to go to simulation tab and select edit simulation and select DC op pnt and click ok at last we need to run the simulation.

For simulation we have used MOSFET with seperate specification, for this we have used net list known as spice netlist. to add netlist first we need to go for spice directiove and type ".lib tsmc018.lib" where .lib is keyword and tsmc018 is the PDf file name with all specification.
#### CIRCIUT DIAGRAM IN LT SPICE
![Screenshot (91)](https://github.com/user-attachments/assets/ed73f70a-655d-4ee8-a057-44dda7496c4b)

#### OUTPUT OF DC OPERATING POINT
![Screenshot (92)](https://github.com/user-attachments/assets/1e1fc722-f884-4c78-bf13-e93906aa3fcd)

This confirmes the mosfet is working in the Saturation Region.VGD is Greater than VTH Hence it is in Saturation Region(VGD>VTH).
### 5.TRANSIENT ANALYSIS
Generate sine waveform with specified amplitude and frequency so we need to right click on the V1 and select advanced and we need select sine we get option to type the specification. for DC offset = 0.9V for amplitude = 50mV for frequency = 1KHz.To do transient analysis and calculating gain to do transient analysis we need to click on simulation tab and select edit simulation in the popup window we need to select transient and give the specifications for stop time : 10ms for time to start saving data : 0s and click ok and run the simulation.

![image](https://github.com/user-attachments/assets/07d8f6ef-8180-4f5e-a821-3760ef7990e1)

The Voltage Gain is (1.752-1.738)V/100mV = 0.14 v/v .
### 6.AC ANALYSIS

Follow these steps to set up an AC analysis in LTspice:
1. In the Small Signal AC Analysis box, set AC Amplitude to 1.
2. Go to the Simulation tab and select Edit Simulation Cmd.
3. In the AC Analysis section, configure:
   - Type of sweep:Decade  
   - Number of points per decade: 20  
   - Start frequency: 0.1 Hz  
   - Stop frequency: 1 THz  
4. Click OK and run the simulation.
This will generate the frequency response of the circuit.

![image](https://github.com/user-attachments/assets/e48da286-d4d5-48ae-b589-f37fda919bc5)

### To increase the Voltage Gain the Rd changed to 10k ohm and to maintain the ID W is changed to 0.235um 
##### OUTPUT OF OPERATING POINT

![image](https://github.com/user-attachments/assets/37d72449-a1fd-4d96-8d69-6fdafb020f98)

This confirmes the mosfet is still working in the Saturation Region.VGD is Greater than VTH Hence it is in Saturation Region(VGD>VTH).

#### OUTPUT OF TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/991e23cb-68f2-42f5-a55f-db2073a15873)

The Voltage Gain is (1.32-1.17)V/100mV = 1.5 v/v .
#### OUTPUT OF AC RESPONSE
![image](https://github.com/user-attachments/assets/dab62bd2-792d-4fde-8df9-eeb140a7bd01)

