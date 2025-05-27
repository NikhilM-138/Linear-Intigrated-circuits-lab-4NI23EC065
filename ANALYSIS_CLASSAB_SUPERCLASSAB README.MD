# High-Performance Super Class AB OTA for Low Power Analog Signal Processing 

## 1.ABSTRACT 
This work presents a Super Class AB CMOS Operational 
Transconductance Amplifier (OTA) that significantly 
outperforms traditional Class AB OTAs in terms of slew 
rate, gain-bandwidth product (GBW), and current efficiency. 
By combining adaptive biasing with local common-mode 
feedback (LCMFB), the proposed OTA delivers dynamic 
current boosting directly to the output, minimizing power 
loss and complexity. Compared to conventional Class AB 
designs, it offers enhanced stability, reduced area, and 
superior performance at low supply voltages. Fabricated in 
0.5-μm CMOS technology, the OTA achieves over 200× 
improvement in slew rate and 3.6× GBW enhancement, 
making it ideal for modern analog applications.

## 2.INTRODUCTION 
In modern analog and mixed-signal VLSI systems, 
Operational Transconductance Amplifiers (OTAs) are 
fundamental building blocks used in filters, analog-to-digital 
converters (ADCs), sample-and-hold circuits, etc. These 
systems often require:

1.Low-voltage operation (due to shrinking supply 
voltages in CMOS processes), 
2.High power efficiency (for battery-powered 
devices), 
3.High slew rate and gain-bandwidth product 
(GBW) for fast signal processing. 


Traditional Class A OTAs are power-hungry because the 
output current is limited by a fixed bias current. The need 
for high performance at low power gave rise to Class AB 
OTAs, which use adaptive biasing to dynamically increase 
output current when needed. However, existing Class AB 
solutions often suffer from complexity, instability, or 
degraded small-signal performance. 

The Super Class AB OTA addresses these challenges by 
integrating two key techniques: 
1.Adaptive Biasing: Increases dynamic current only 
when a large input signal is applied.
2.Local Common-Mode Feedback (LCMFB): 
Enhances output current boosting and current 
efficiency by introducing local feedback through 
resistors in the load.

## 3. PROPOSED METHODOLOGY / SYSTEM DESIGN 

#### 3.1 OTA ARCHITECTURE (EXPLAINING THE SCHEMATIC) 
a)Input Differential Pair: Transistors M1 and M2 
form the core differential input. Their gates receive 
Vin− and Vin+, respectively. 
b)Adaptive Bias Current Sources: IB provides a 
small quiescent current that increases dynamically 
during large signal transitions. 
c)Active Loads with Feedback: M1A, M2A and 
M1B, M2B form current mirrors and serve as 
active loads for the input pair. 
d)Local Common-Mode Feedback (LCMFB): 
Resistors R1 and R2 feed back the average of the 
drain voltages of M1 and M2 to their common 
gates. This feedback balances the operating points 
and boosts the current further during transients. 
e)Output Stage: M3 and M4 deliver the final output 
to Vout. These are driven by currents generated 
through the active loads and mirrors. 

#### 3.2 Operating Principle 
a)Small-Signal Condition: For small differential 
inputs, the OTA behaves as a Class A amplifier, 
maintaining quiescent currents through all 
transistors. 
b)Large-Signal Input: When the input voltage 
difference increases, adaptive biasing boosts the 
tail current in the differential pair, leading to an 
increased output current. 
c)LCMFB (Low-Voltage Common-Mode 
Feedback): LCMFB generates differential voltages 
across resistors R1 and R2, driving the gates of the 
mirror transistors to dynamically increase the 
output current without needing external feedback 
loops. 
d)Slew Rate: Due to the absence of fixed output 
currents, the OTA exhibits a much higher slew rate 
compared to conventional OTAs.

## 4. IMPLEMENTATION / EXPERIMENTAL SETUP 
1. CMOS Technology: Fabricated using 0.5-μm 
CMOS process. 
2. Bias Current: 10 μA typical quiescent current. 
3. Load: Measured with 80 pF capacitive load. 
4. Circuit Configuration: Used unity-gain feedback 
for transient tests. 
5. Test Setup:1 MHz square wave input,Outputs measured directly from the chip (no buffer) and  Measured key performance: slew rate, GBW, gain, current efficiency. 
   

## 5.CIRCUIT DIAGRAM 
![image](https://github.com/user-attachments/assets/9c522481-8ca2-40be-a52e-99447615bcfa)

![image](https://github.com/user-attachments/assets/d06775ec-e531-4303-933d-067374cd49bf)

## 6.DC ANALYSIS 

![image](https://github.com/user-attachments/assets/61d8e91a-108a-48bd-8e0f-34c4f34d8469)


  The DC analysis of the Super Class AB OTA is 
performed to determine the steady-state operating points of 
all MOSFETs and ensure they operate in the saturation 
region. In the circuit, the differential input pair (M1, M2) is 
biased by a constant tail current, mirrored through M6 and 
M7. The active load is formed by current mirror transistors 
(M1A, M1B, M2A, M2B), which ensure proper current 
steering. For each MOSFET, the condition VDS > VGS – 
VTH  is maintained to ensure saturation. The local common
mode feedback (LCMFB), implemented using resistors R1 
and R2, sets the gate voltages of M3 and M4 to fix the 
output common-mode voltage around 0.9 V (for VDD = 
1.8 V). This analysis also confirms the correct bias currents 
and quiescent power consumption of the circuit. As per the 
reference paper, the OTA consumes approximately 200 µW 
in quiescent mode and is correctly biased for linear 
operation.


## 7.TRANSIENT ANALYSIS
### CIRCUIT DIAGRAM
![image](https://github.com/user-attachments/assets/ff099d44-8fab-4f81-9609-0fe34a200ae6)

 Transient analysis is used to evaluate the large
signal dynamic performance of the Super Class AB OTA, 
particularly its slew rate. In this test, a large step input 
voltage is applied to the OTA in a unity-gain configuration, 
and the output response is observed over time. The circuit is 
designed to deliver a fast output transition due to the 
dynamic current boosting provided by the flipped voltage 
follower (FVF) stage and local feedback paths. The slew 
rate is calculated from the steepest slope of the output 
waveform during the transition, using the formula 
Slew Rate=ΔV/Δt. As reported in the reference paper, the 
OTA achieves a slew rate of approximately 375 V/µs for a 
capacitive load of 80 pF. This high slew rate demonstrates 
the effectiveness of the super class AB architecture in 
driving large capacitive loads quickly while maintaining low 
quiescent power consumption.


## 8. AC ANALYSIS
![image](https://github.com/user-attachments/assets/a558c088-bb60-46a5-84f5-dac849937a80)
AC analysis is performed to determine the small
signal voltage gain and frequency response of the Super 
Class AB OTA. In this test, a small AC signal is applied at 
the input while the frequency is swept over a wide range, 
typically from 1 Hz to several MHz. The OTA is configured 
in open-loop to measure the frequency-dependent gain 
Av=Vout/Vin . The practical AC simulation showed a mid
band gain of approximately 35 dB, which aligns closely 
with the expected performance as discussed in the reference 
paper. This gain is achieved without the use of cascode 
stages, relying instead on carefully sized output transistors 
and proper biasing to maximize intrinsic gain. The result 
confirms that the OTA operates effectively in the small
signal regime, with sufficient gain for analog signal amplification in low-voltage applications. 


## 9.SLEW RATE
### CIRCUIT DIAGRAM 
![image](https://github.com/user-attachments/assets/33817607-e6f1-4c89-a22f-c390481a367d)


 ### OUTPUT
 ![image](https://github.com/user-attachments/assets/cca3b411-aaf1-4151-bc2e-7ee7cdd6058f)

 Slew rate analysis is conducted to evaluate the 
OTA's large-signal response capability. The OTA is 
configured in unity-gain feedback, and a large input voltage 
step (e.g., 0.9 V to 1.3 V) is applied. The output waveform is 
monitored, and the maximum rate of voltage change is 
measured during the transition period. The slew rate is 
calculated as SR=ΔV/Δt. In the practical simulation, the 
OTA achieved a slew rate of approximately 200 V/µs, 
demonstrating strong large-signal performance. This high 
slew rate is a key advantage of the super class AB 
architecture, which enables dynamic current boosting 
through flipped voltage follower stages. The result confirms 
that the OTA can rapidly drive capacitive loads, supporting 
high-speed signal processing applications.

## 10.DC SWEEP
![image](https://github.com/user-attachments/assets/c4342ac1-27ec-4c83-ba09-dcf99fc6120c)

![image](https://github.com/user-attachments/assets/87be303d-3444-4de5-aeac-5bbda5ff1137)

DC sweep analysis is used to evaluate the input
output transfer characteristics of the OTA and determine its 
input common-mode range and output swing limitations. In 
this test, the differential input voltage is swept slowly across 
a range (typically from 0 V to 1.8 V), and the corresponding 
output voltage is observed. The objective is to identify the 
linear operating region of the OTA, where the output 
faithfully tracks the input without distortion or clipping. 
From the practical simulation, it is observed that the OTA 
maintains linearity across a significant portion of the input 
range, with the output staying within its swing limits. This 
analysis also confirms that all transistors remain in the 
saturation region during normal operation, ensuring valid 
gain and linearity. The results are consistent with the 
behavior described in the reference paper, which highlights 
the importance of setting proper bias voltages and ensuring 
headroom to maximize the usable input and output range in 
low-voltage operation.

## 11.NOISE ANALYSIS 
Noise analysis was carried out to evaluate the 
spectral noise performance of the OTA. Using the .noise 
simulation in LTspice, the output noise spectral density was 
plotted over a frequency range of 1 Hz to 1 MHz. The 
integrated output-referred noise was found to be in the range 
of a few hundred nanovolts RMS, with input-referred noise 
values remaining low across the operational bandwidth. The 
results are consistent with the reference paper, which 
demonstrates that the super class AB OTA maintains a low
noise profile despite operating at low voltage and power. 
This confirms that the OTA is suitable for analog signal 
processing applications that require good noise performance, 
such as sensor interfaces and audio amplifiers.

## 12.POWER ANALYSIS
Power analysis was performed using .op (operating 
point) simulation to determine the static power consumption 
of the OTA. The supply voltage was set to 1.8 V, and the 
current drawn from the source was measured. The calculated 
quiescent power consumption was approximately 180
200 µW, which closely matches the value reported in the 
reference paper. This low power consumption is achieved 
through careful biasing and the use of current-efficient 
mirror structures. The super class AB configuration further 
ensures that dynamic current boosting is only activated 
during large signal swings, keeping the average power low 
during normal operation.

## 13.CMRR (Common-Mode Rejection Ratio) Analysis
CMRR analysis was conducted by applying a 
common-mode input signal (same signal to both Vin+ and 
Vin−) and measuring the output deviation. The differential
mode gain was also measured separately. The simulated 
CMRR was found to be around 60–70 dB, which is in good 
agreement with the performance expected from the 
symmetrical OTA topology described in the reference paper. 
The use of matched transistors and local common-mode 
feedback ensures high rejection of common-mode signals, 
making the OTA robust against power supply ripple and 
noise injection at the input stage. 

## 14.PSRR (Power Supply Rejection Ratio) Analysis
PSRR analysis was done by applying a small AC 
signal on the supply voltage (VDD) and observing the ripple 
at the output. The simulated PSRR was found to be 
approximately 55–65 dB, which is consistent with 
theoretical expectations. The circuit topology inherently 
provides good power supply isolation due to the current 
mirrors and the differential nature of the design. As 
highlighted in the reference paper, maintaining high PSRR 
is crucial for analog circuits operating in noisy environments 
or sharing supply rails with digital blocks.

## 15. Results and Discussion 

The designed Super Class AB OTA was simulated 
using LTspice to validate its performance metrics and 
compare them with the theoretical expectations described in 
the reference paper. Key parameters such as gain, 
bandwidth, slew rate, noise, power consumption, CMRR, 
and PSRR were extracted using appropriate DC, AC, 
transient, and noise analyses. 

The DC analysis confirmed that all MOSFETs 
operate in the saturation region, with stable node voltages 
and correct bias currents throughout the circuit. The OTA 
maintained a balanced output common-mode voltage of 
approximately 0.9 V, achieved through the local common
mode feedback (LCMFB) mechanism using resistors R1 and 
R2. The simulated static power consumption was found to 
be around 180–200 µW, which is consistent with the 
reference design that prioritizes power efficiency. 

The AC analysis yielded a mid-band gain of 
approximately 35 dB, which is close to the 40 dB reported 
in the reference paper. This gain was achieved without the 
use of cascode structures, validating the design’s efficiency 
in achieving sufficient voltage amplification in a single
stage OTA. The gain bandwidth product (GBW) was 
found to be in the range of 5–10 MHz, which is suitable for 
moderate-speed analog signal processing. 

The slew rate measured from transient analysis 
was approximately 200 V/µs, compared to the theoretical 
value of 375 V/µs stated in the paper. Although slightly 
lower, this value still demonstrates the high-speed behavior 
enabled by the Super Class AB architecture, where dynamic 
current boosting occurs during large signal transitions. The 
result confirms the effectiveness of the flipped voltage 
follower (FVF) stage in enhancing slew performance while 
maintaining low quiescent power. 

The noise analysis revealed low output-referred 
and input-referred noise levels, particularly in the mid to 
high frequency range. The OTA exhibited typical 1/f noise 
behavior at low frequencies and a flat thermal noise floor at 
higher frequencies, in agreement with CMOS noise 
characteristics. 

CMRR and PSRR were also evaluated. The OTA 
achieved a simulated CMRR of around 60–70 dB and 
PSRR of 55–65 dB, closely matching the expected values 
from the paper. These results confirm the circuit's robustness 
against common-mode and supply voltage disturbances, 
making it suitable for mixed-signal environments. 

In conclusion, the simulated Super Class AB OTA 
closely matches the theoretical performance outlined in the 
reference paper. While minor deviations were observed in 
slew rate and gain, the overall design meets the objectives of 
high slew rate, moderate gain, low power consumption, and 
good noise immunity. The OTA is well-suited for 
applications such as switched-capacitor filters, sensor 
interfaces, and low-power analog signal processing.

## Simulation vs Theoretical Comparison 

| **Parameter**                        | **Theoretical Value**      | **Simulated Value (LTspice)** | **Remarks**                                          |
|-------------------------------------|-----------------------------|-------------------------------|------------------------------------------------------|
| Mid-Band Gain                       | ~40 dB                      | 35 dB                         | Slightly lower; no cascode used                      |
| Gain Bandwidth Product (GBW)        | ~5–10 MHz (expected)        | 5–10 MHz                      | Matches theoretical range                            |
| Slew Rate                           | ~375 V/µs                   | 200 V/µs                      | Slightly lower; FVF still enhances speed             |
| Power Consumption (Static)          | ~200 µW                     | 180–200 µW                    | Very close to expectation                            |
| Output Common-Mode Voltage          | –0.9 V                      | –0.9 V                        | Balanced by LCMFB via R1 and R2                      |
| Input/Output Noise Behavior         | CMOS 1/f and thermal noise  | Matches CMOS profile          | Low noise, thermal dominated at high freq            |
| Common-Mode Rejection Ratio         | ~60–70 dB                   | 60–70 dB                      | Strong CMR performance                               |
| Power Supply Rejection Ratio        | ~55–65 dB                   | 55–65 dB                      | Good immunity to VDD fluctuations                    |
| MOSFET Region of Operation          | Saturation                  | Saturation                    | Confirmed via DC analysis                            |

## Characteristic Comparison – Class AB OTA vs Super Class AB OTA

| **Characteristic**             | **Class AB OTA**                                              | **Super Class AB OTA**                                               |
|-------------------------------|----------------------------------------------------------------|------------------------------------------------------------------------|
| **Biasing**                   | Fixed quiescent current                                        | Adaptive biasing with dynamic current boosting                        |
| **Output Current Capability** | Limited during large signals                                   | Increases dynamically with input signal amplitude                     |
| **Slew Rate**                 | Moderate                                                       | High due to flipped voltage follower and adaptive biasing             |
| **Gain**                      | Moderate                                                       | Higher due to efficient single-stage amplification                    |
| **Bandwidth**                 | Limited                                                        | Wider bandwidth achieved                                              |
| **Noise Performance**         | Higher due to static bias                                      | Lower with improved thermal noise behavior                            |
| **Power Consumption**         | Constant (set by bias current)                                 | Efficient; low at rest, increases during large signal events          |
| **Common-Mode Rejection (CMRR)** | Moderate                                                   | Higher due to better differential handling                            |
| **Power Supply Rejection (PSRR)** | Moderate                                                  | Improved due to dynamic regulation                                    |
| **Output Common-Mode Control** | Basic or external feedback                                    | Local common-mode feedback (LCMFB) stabilizes output                  |
| **Complexity**                | Simpler                                                        | More complex due to additional control circuitry                      |
| **Suitability**               | General-purpose analog processing                              | High-speed, low-power, and dynamic analog applications                |


## 16. Inference

1. **Adaptive Biasing Improves Dynamic Behavior**  
   The Super Class AB OTA exhibits enhanced slew rate and large-signal performance due to adaptive biasing. This allows the tail current to increase dynamically during high differential input, which is not present in Class AB designs.

2. **FVF Stage Boosts Slew Rate Performance**  
   The flipped voltage follower (FVF) stage helps in fast charging/discharging of output nodes. Although the simulated slew rate is slightly lower than theoretical, this deviation may arise due to parasitic capacitances and device mismatch in the practical layout.

3. **Gain Slightly Lower than Theoretical Due to Loading Effects**  
   The mid-band gain obtained from simulation is slightly lower than expected. This is primarily due to loading effects from parasitic elements and the absence of ideal current sources, which reduce the effective output resistance.

4. **Output Common-Mode Voltage Well-Regulated**  
   The simulated output common-mode voltage remains stable due to the LCMFB mechanism. Minor variations from the theoretical value could be due to resistor mismatch in R1 and R2 or finite gain in the feedback loop.

5. **GBW Within Expected Range Despite Circuit Simplification**  
   The gain-bandwidth product achieved is consistent with theoretical predictions, although small shifts may occur due to non-ideal transistor parameters, such as mobility reduction at higher frequencies.

6. **Power Consumption Matches Expectation with Minor Deviations**  
   Simulated power consumption lies close to theoretical values. Small deviations are attributed to bias current variation across process corners and switching activity during transient behavior.

7. **CMRR and PSRR Match Target Values with Slight Variation**  
   While the simulated CMRR and PSRR align with expected levels, slight differences may result from asymmetries in the differential pair or non-ideal power supply rejection in mirror stages.

8. **Noise Characteristics Reflect CMOS Behavior with Layout Influences**  
   Simulated noise profiles match theoretical expectations, showing 1/f noise at low frequencies and flat thermal noise at higher frequencies. Minor differences may arise due to model inaccuracies in the noise corner frequency or layout parasitics affecting the noise path.


## 17. Conclusion

The proposed **Super Class AB OTA** achieves:

- Very high slew rate and GBW.
- Optimal current efficiency.
- Low static power consumption.
- Simple design compatible with low-voltage CMOS.

The combination of **adaptive biasing** and **LCMFB** creates a compact and robust amplifier architecture, suitable for use in high-performance, low-power analog systems like wireless receivers, ADC buffers, and filter designs.

---

## 18. Applications

1. Switched-capacitor and continuous-time filters  
2. Low-power Analog-to-Digital Converters (ADCs)  
3. Portable and wearable electronics  
4. Sensor front-end amplifiers in biomedical devices  
5. Sample-and-hold circuits for data converters  
6. Wireless communication transceivers  
7. Analog audio signal amplifiers  
8. Low-voltage analog buffers for VLSI testing  
9. Integrated instrumentation amplifiers  
10. Mixed-signal system-on-chip (SoC) analog blocks  

---

## 19. Future Work

- **Process Scaling**: Implement in sub-100nm nodes to explore behavior at even lower voltages.
- **Fully Differential Design**: For better common-mode rejection.
- **Programmable Biasing**: Use digital control for GBW/power tuning.
- **OTA Integration**: Embed in full systems like SC filters, delta-sigma ADCs.

---

## 20. Literature Survey and References

### Key Papers

1. A.J. López-Martín et al., IEEE JSSC, 2005 – Original design of Super Class AB OTA.  
2. Degrauwe et al., 1982 – Adaptive biasing amplifier design.  
3. Harjani et al., 1999 – Early Class AB CMOS OTAs.  
4. Ramirez-Angulo et al., 2002 – Local CMLFB to enhance slew rate and bandwidth.  
5. Razavi, B., *Design of Analog CMOS ICs*, McGraw-Hill – Core analog IC design text.  

---

### References

[1] K. de Langen and J. H. Huijsing, “Compact low-voltage power-efficient operational amplifier cells for VLSI,” IEEE J. Solid-State Circuits, vol. 33, no. 10, pp. 1482–1496, Oct. 1998.  

[2] M. Degrauwe, J. Rijmenants, E. A. Vittoz, and D. Man, “Adaptive biasing CMOS amplifier,” IEEE J. Solid-State Circuits, vol. SC-17, no. 3, pp. 522–528, Jun. 1982.  

[3] L. Callewaert and W. Sansen, “Class AB CMOS amplifiers with high efficiency,” IEEE J. Solid-State Circuits, vol. 25, no. 2, pp. 684–691, Jun. 1990.  

[4] R. Castello and R. P. Gray, “A high-performance micropower switched-capacitor filter,” IEEE J. Solid-State Circuits, vol. SC-20, no. 6, pp. 1122–1132, Dec. 1985.  

[5] S. L. Wong and C. A. T. Salama, “An efficient CMOS buffer for driving large capacitive loads,” IEEE J. Solid-State Circuits, vol. SC-21, no. 3, pp. 464–469, Jun. 1986.  

[6] R. Kline, B. J. Hosticka, and H. J. Pfleiderer, “A very-high-slew-rate CMOS operational amplifier,” IEEE J. Solid-State Circuits, vol. 24, no. 3, pp. 744–746, Jun. 1989.
