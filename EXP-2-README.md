## EXPERIMENT NO.2
# MOS DIFFRENTIAL AMPLIFIER CIRCUITS
### 1. INTRODUCTION
  
  A MOSFET differential amplifier is a critical component in analog circuit design, designed to amplify the difference between two input signals while suppressing any common-mode signals (noise or interference that appears equally on both inputs). This unique property makes it highly effective in applications requiring precision and noise rejection, such as operational amplifiers, sensor signal conditioning, and communication systems. Unlike single-ended amplifiers, which amplify one input signal relative to ground, a differential amplifier enhances signal integrity by rejecting common-mode noise and interference. The circuit typically consists of two matched MOSFETs arranged symmetrically, sharing a common current source. The high input impedance and low output impedance of MOSFETs contribute to the amplifier's high gain, excellent linearity, and low power consumption. Modern designs often incorporate advanced configurations to improve performance further, making these amplifiers ideal for precision applications in fields like instrumentation, telecommunications, and integrated circuit design.
  
   ![images](https://github.com/user-attachments/assets/37fda217-e244-4b72-b054-310a01e52785)
  
### 2. DIFFERENCE B/W MOS DIFFRENTIAL AMPLIFIER & SINGLE STAGE AMPLIFIER


|Feature | MOS Differential Amplifier | Single-Stage Amplifier |
|---------|----------------------------|------------------------|
| **Number of Inputs** | Two (Vin+ and Vin-) | One (Vin) |
| **Functionality** | Amplifies the difference between two inputs, rejecting common-mode signals | Amplifies a single input referenced to ground |
| **Common-Mode Rejection** | High (CMRR) | Low, amplifies noise along with the signal |
| **Gain** | Differential gain: `Ad = gm * RD` | Voltage gain: `Av = gm * RD` |
| **Symmetry** | Symmetric circuit design | Asymmetric operation |
| **Components** | Two MOSFETs, current source, load resistors (or active load) | Single MOSFET with a load resistor (or active load) |
| **Output** | Differential output (Vout+ and Vout-) | Single-ended output |
| **Applications** | Op-amps, instrumentation amplifiers, sensor interfaces | Audio amplifiers, RF amplifiers, signal boosters |
| **Noise Immunity** | High (common-mode rejection) | Low (prone to noise) |
| **Power Consumption** | Higher (due to dual transistors and biasing circuit) | Lower (single transistor) |
| **Coupling Capacitor** |Not commonly required because differential amplifiers inherently reject DC offsets and common-mode noise. The circuit operates with a stable biasing scheme without external DC blocking.|Essential at input and output to block DC components, prevent biasing shifts, and ensure proper AC signal transmission. Without coupling capacitors, DC bias levels from one stage could interfere with the next, leading to signal distortion or improper operation.|

SINGLE STAGE AMPLIFIER DIFFERENT CONFIGURATIONS

<img src="https://github.com/user-attachments/assets/aed21a53-76a6-4223-b510-6273ff7c0503" alt="Single Stage Amplifier" width="500">

### 3. AIM OF THE EXPERIMENT  

The aim of this experiment is to design, analyze, and simulate a **MOSFET differential amplifier** to understand its **operation, gain characteristics, and common-mode rejection ratio (CMRR)**. Additionally, the experiment explores different differential amplifier configurations and their impact on performance by:  

1. **Using a Resistor as a Constant Current Source**  
   - Examining the basic differential pair with a simple resistive tail current.  

2. **Replacing the Source Resistor (Rss) with a Constant Current Source**  
   - Improving gain stability and CMRR.  

3. **Replacing the Current Source with an NMOS Transistor**  
   - Implementing an active current source for better performance.  

4. **Replacing the Load Resistors (Rd) with PMOS Transistors**  
   - Using an active load to enhance gain and differential output swing.  
   - In this configuration, all passive components (resistors) are replaced by MOSFETs, making the circuit fully active, improving gain, and increasing linearity.

#### DESIGN QUESTION:
**Design and Analyze the Differential Amplifier for the following specs. VDD = 2V , P <= 2.2mV , VICM = 1.2V , VOCM = 1.25V ,     VP = 0.4V.**

### 4. ANALYTICAL DESIGN APPROACH
GIVEN:<br>
VDD=2.2V <br>
P<=2.2mW <br>
VP=0.4V <br>
VICM=1.2V <br>
VOCM=1.25V <br>

The power of the overall circuit is given by,<br>
P = V*ISS <br>
ISS = P/VDD , 2.2m/2.2 = 1mA. <br>
ISS= 1mA. <br>

ISS= ID1 + ID2 <br>

Since ID1 and 𝐼𝐷2 are equal in an ideal MOSFET differential amplifier due to symmetrical circuit design, identical transistor characteristics, and a constant tail current source ensuring equal current division.<br>
ID1 = ID2 =ISS/2 = 0.5mA.<br> 

designig RSS Value:<br>

RSS= VP/ISS = 0.4/1m = 0.4k ohm <br>

designig RD Value:<br>

RD= (VDD - VOCM)/ID1 <br>
  = (2.2-1.25)/0.5m<br>
RD= 1.9k ohm <br>

### 5. SIMULATION OF MOS DIFF AMPLIFIER USING A RESISTOR AS A CONSTANT TAIL CURRENT SOURCE.
#### 1. DC ANALYSIS:-

Built the circuit as per the circuit diagram below <br>
![image](https://github.com/user-attachments/assets/327f6f52-3ca7-497a-8710-936be8ff803f)<br>

To perform the DC Analysis click the edit simulation and select the DC OP point(.op).<br>

![image](https://github.com/user-attachments/assets/50dd6b21-c65e-49e2-ae59-20c673337198)<br>

**The Output matches all the required  design values.** <br>
This shows two MOSFETS working in the saturation. 
VGS > VTH & VDS > VOV<br>
**VGS = 1.2-0.4 = 0.8V > 0.366V(VTH),** <br>
**VDS = 1.25-0.4 = 0.85V > (0.8-.366)V = 0.85 > 0.434V (VOV).** <br>

#### 2.TRANAIENT ANALYSIS 
To perform Transient analysis click the edit Simulation then click on Transient Analysis.<br>
Now give the stop time as 10ms and Run.

![image](https://github.com/user-attachments/assets/803a5d72-a341-4064-8358-e0a831032d10)
The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.


For Applying the Amplitude of the input signal should be **vgs<<2VOV**.
vgs<<2*(VGS-VTH). <br>
vgs<<2*(0.8-0.366).<br>
**vgs<<0.868V**

The Theoretiacal Gain = **-gmRD** .<br>
gm= (2*ID)/VOV = (2 * 0.5m)/0.434 = 2.304m Simeon. <br>
AV = -(2.304m  * 1.9k) = **- 4.377 V/V** <br>

The Practical Gain = **VOUTpp/VINpp** . <br>
AV = -443.08mV/100mV = **-4.4308 V/V**. <br>


Gain in db scale:-
Av = **20*log(Voutpp/Vinpp).** <br>
Av = **12.929 db**. <br> 

#### DIFFERENTIAL GAIN:-
![image](https://github.com/user-attachments/assets/ab5c9ceb-c682-4255-adf7-03687b51a69e)

From the graph The Differential Gain = -900mV/100mV = **-9 V/V**.<br>
Gain in db scale is = 20*log(Votpp/vinpp) = 19.084 V/V.

#### 3. AC ANALYSIS
To perform AC Analysis click the edit simulation then click on AC Analysis.<br>
Now select the type of sweep as **Decade** , No.of points as **10m** and then give **Starting frequency as 1Hz & Ending as 1MHz** then Run.<br> <br>

![image](https://github.com/user-attachments/assets/cd89e240-2e0f-43c8-8b26-bf47754e2c3e)

From the above graph we can get the **Band-Width & Gain** of the circuit.<br>
The Band Width of the Circuit is **22.205 GHz & 12.11db**.
#### DIFFERENTIAL AC ANALYSIS:-
![image](https://github.com/user-attachments/assets/6ad475ed-8132-4dab-a1c3-d4bae1e77ddc)

From the above graph we can get the **Band-Width & Gain** of the circuit.<br>
The Band Width of the Circuit is **22.205 GHz & 18.13db**.
#### 4.Varriying the VICM VOLTAGE.
First we are finding the range of the VICM.<br>
**VICM(min) = VTH + VP**.<br>
VICM(min) = 0.366+0.4 .<br>
**VICM(min) = 0.766 V**.<br>

**VICM(max) = VOCM + VTH**. <br>
VICM(max) = 1.25+0.366 .<br>
**VICM(max) = 1.616 V**.<br>

**i)Giving the input as VICM(min):-**
##### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/aef99998-5e3c-4886-b033-0f44145f4aa2)


The Paramet values are:-
 - VGS = 0.6V.
 - IDM1 = 0.1mA.
 - VP = 0.159V.
 - VDS = 1.6V.
 - IRSS = 0.398mA.
 - VOCM = 1.8217V.
 - VICM = 0.8V.
This shows MOSFET is still working in Saruration Region.
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/1e8f7589-a223-4cbe-8098-6d2d76bdb806)


Gain is = -331.407m/100m = **-331.407 V/V**
The gain has been reduced -331.407 V/V .
##### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/5b6f1f20-68bb-4128-ae73-637516d376e6)

The Bandwith is same. **22.205 GHZ** .<br>

**ii)Giving the input as VICM(max):-**
##### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/309e640f-0d79-4deb-85c8-60a7e89d84e9)

The Paramet values are:-
 - VGS = 1.1V.
 - IDM1 = 0.750mA.
 - VP = 0.6V.
 - VDS = 0.174V.
 - IRSS = 1.5mA.
 - VOCM = 0.774V.
 - VICM = 1.7V.
   
   **This MOSFET IS NOT WORKING IN SATURATION REGION.(Vds<Vov).**
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/0918b750-6b15-4589-938f-f811e4559ab2)

Gain is = -30.3m/100m = **-0.303 V/V**.<br>
The gain has been reduced -0.303 V/V .
##### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/c5221a9b-d80e-4646-be15-d0dad3a7270b)


### 6.SIMULATION OF MOS DIFFERENTIAL AMPLIFIER WITH CONSTANT CURRENT SOURCE IN PLACE OF SOURCE RESISTOR (Rss)
#### 1.DC ANALYSIS
Built the circuit as per the circuit diagram below <br>
![image](https://github.com/user-attachments/assets/a336835a-5ec6-4569-aabe-ead7ea38e1d9)

Follow the same steps to perform DC Analysis.
![image](https://github.com/user-attachments/assets/d4aff175-f4bd-431f-9fa1-7f8088d7990c)
**The Output matches all the required  design values.** <br>
This shows two MOSFETS working in the saturation. 
VGS > VTH & VDS > VOV<br>
**VGS = 1.2-0.4 = 0.8V > 0.366V(VTH),** <br>
**VDS = 1.25-0.4 = 0.85V > (0.8-.366)V = 0.85 > 0.434V (VOV).** <br>

#### 2.TRANAIENT ANALYSIS
Follow the same steps to perform Transient Analysis.

![image](https://github.com/user-attachments/assets/eda338a2-b380-40da-8405-349d3cdb0e41)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>


For Applying the Amplitude of the input signal should be **vgs<<2VOV**.
vgs<<2*(VGS-VTH). <br>
vgs<<2*(0.8-0.366).<br>
**vgs<<0.868V**

The Theoretiacal Gain = **-gmRD** .<br>
gm= (2*ID)/VOV = (2 * 0.5m)/0.434 = 2.304m Simeon. <br>
AV = -(2.304m  * 1.9k) = **- 4.377 V/V** <br>

The Practical Gain = **VOUTpp/VINpp** . <br>
AV = -443.094mV/100mV = **-4.43094 V/V**. <br>

Gain in db scale:-
Av = **20*log(Voutpp/Vinpp).** <br>
Av = **12.8875 db**. <br> 

#### DIFFERENTIAL GAIN:-
![image](https://github.com/user-attachments/assets/ba492238-f118-42ad-8a84-6285147f4043)


From the graph The Differential Gain = -900mV/100mV = **-9 V/V**.<br>
Gain in db scale is = 20*log(Votpp/vinpp) = 19.084 V/V.<br>
#### 3.AC ANALYSIS
Follow the same steps to perform AC Analysis.

![image](https://github.com/user-attachments/assets/dcf59943-d203-4b63-baca-189b5003fea7).

From the above graph we can get the **Band-Width & Gain** of the circuit.<br>
The Band Width of the Circuit is **22.205GHz & 12.11db**.

#### 4.Varriying the VICM VOLTAGE.

**i)Giving the input as VICM(min):-**
##### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/f051895d-8b0d-4411-a336-4286e022b868)

The Paramet values are:-
 - VGS = 0.8V.
 - IDM1 = 0.5mA.
 - VP = -0.099V.
 - VDS = 1.35V.
 - IL = 1mA.
 - VOCM = 1.25V.
 - VICM = 0.7V.
This shows the MOSFET is working in Saturation Region
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/3590ab33-a2f4-4a1b-a9eb-d45fbcfd7ba1)

Gain is = -416.10m/100m = **-4.1610 V/V**.<br>
The gain has been reduced -4.1610 V/V .

##### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/0d341867-5009-407d-b19c-684d74e823ef)

The Bandwith is same. **21.25 GHZ** .<br>

**ii).Giving the input as VICM(max):-**
##### 1.DC ANALYSIS
![Screenshot (184)](https://github.com/user-attachments/assets/454c931b-a923-416a-8261-b2cdb568aa56)

The Paramet values are:-
 - VGS = 0.826V.
 - IDM1 = 0.5mA.
 - VP = 0.876V.
 - VDS = 0.376V.
 - IL = 1mA.
 - VOCM = 1.25V.
 - VICM = 1.7V.
   
**This MOSFET IS NOT WORKING IN SATURATION REGION.(Vds<Vov).**
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/6bd9a7aa-77f1-430f-8e00-4f9b88de2cf4)

Gain is = -276.72m/100m = **-2.76272 V/V**.<br>
The gain has been reduced -2.76272 V/V .
##### 3.AC ANALYSIS
![Screenshot (183)](https://github.com/user-attachments/assets/cdc85b89-61d9-4788-b8a4-987b6daa111b)

The Bandwith has increased to **32.143 GHZ** .<br>

### 7.SIMULATION OF MOS DIFFERENTIAL AMPLIFIER BY REPLACING THE CURRENT SOURCE WITH AN NMOS TRANSISTOR
For designing the Voltage(Vb) of the MOSFET M3:<br>
**VGD<=VTH**<br>
**Vb-VP <= VTH** <br>
**Vb-0.4 <= 0.366V**
**Vb <= 0.766V**
#### 1.DC ANALYSIS
Built the circuit as per the circuit diagram below <br>
![image](https://github.com/user-attachments/assets/c122843e-c5b4-4056-90f4-7b5feeb76aa0)

Follow the same steps to perform DC Analysis.
![image](https://github.com/user-attachments/assets/80c39c2b-d163-4d09-be5b-127c96778415)

This shows two MOSFETS working in the saturation. 
VGS > VTH & VDS > VOV<br>
**VGS = 1.2-0.4 = 0.8V > 0.366V(VTH),** <br>
**VDS = 1.25-0.4 = 0.85V > (0.8-.366)V = 0.85 > 0.434V (VOV).** <br>
#### 2. TRANSIENT ANALYSIS
Follow the same steps to perform Transient Analysis.

![image](https://github.com/user-attachments/assets/4280a35d-5bbc-4c20-8052-3c36826b4ca3)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>

For Applying the Amplitude of the input signal should be **vgs<<2VOV**.
vgs<<2*(VGS-VTH). <br>
vgs<<2*(0.8-0.366).<br>
**vgs<<0.868V**
The Theoretiacal Gain = **-gmRD** .<br>
gm= (2*ID)/VOV = (2 * 0.5m)/0.434 = 2.304m Simeon. <br>
AV = -(2.304m  * 1.9k) = **- 4.377 V/V** <br>

The Practical Gain = **VOUTpp/VINpp** . <br>
AV = -397.59mV/100mV = **-3.9759 V/V**. <br>

Gain in db scale:-
Av = **20*log(Voutpp/Vinpp).** <br>
Av = **11.989 db**. <br>

Differential Gain:
![image](https://github.com/user-attachments/assets/61d868ce-39e9-4016-8756-fbf9576cbe57)

From the graph The Differential Gain = -800mV/100mV = **-8 V/V**.<br>
Gain in db scale is = 20*log(Votpp/vinpp) = 18.0617 V/V.<br>

#### 3. AC ANALYSIS
Follow the same steps to perform AC Analysis.

![image](https://github.com/user-attachments/assets/652f7a2d-54d3-4db8-8eff-deeadf3e6f6d)


From the above graph we can get the **Band-Width & Gain** of the circuit.<br>
The Band Width of the Circuit is **22.205GHz & 12.11db**

#### 4.Varriying the VICM VOLTAGE.

**i)Giving the input as VICM(min):-**
##### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/afb99dbc-3226-4c43-976c-3549d312bdd7)


The Paramet values are:-
 - VGS = 0.643V.
 - IDM1 = 0.197mA.
 - VP = 0.05V.
 - VDS = 1.7V.
 - ID M3=0.394mA.
 - VOCM = 1.825V.
 - VICM = 0.7V.

This shows the MOSFET is working in Saturaation Region
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/2aec350f-57bc-4025-94ed-d598b93a2cd3)

Gain is = -334.33m/100m = **-3.3433 V/V**.<br>
The gain has been reduced -3.3433 V/V .
##### 3.AC ANALYSIS

![image](https://github.com/user-attachments/assets/733ad779-2ed8-4baa-9ac0-ef87e073d0a3)

The Bandwith & Gain is same. **22.205 GHZ & 10.72db** .<br>

**ii).Giving the input as VICM(max):-**
##### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/e17b59e4-62c8-412e-84b8-f2bbd714a9ed)

The Paramet values are:-
 - VGS = 0.826V.
 - IDM1 = 0.5626mA.
 - VP = 0.835V.
 - VDS = 0.296V.
 - ID M3 = 1.11mA.
 - VOCM = 1.13V.
 - VICM = 1.7V.
   
**This MOSFET IS NOT WORKING IN SATURATION REGION.(Vds<Vov).**
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/e42c6ea6-0dbe-48cb-9d97-03d989fbd859)


Gain is = -200.57m/100m = **-2.0057 V/V**.<br>
The gain has been reduced -2.0057 V/V .
##### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/0e55c2f4-5bb3-4206-87d0-e64114617d80)

The Bandwith has increased to **86.7233GHz & 7db** .<br>
### 7.SIMULATION OF MOS DIFF AMPLIFIER USING REPLACING THE LOAD RESISTORS (𝑅𝐷) WITH PMOS TRANSISTORS
#### 1.DC ANALYSIS 
Built the circuit as per the circuit diagram below <br>
![image](https://github.com/user-attachments/assets/e3cc485a-0055-4af4-90a9-a82a992fc122)

Follow the same steps to perform DC Analysis.
![image](https://github.com/user-attachments/assets/ba2aed5f-43ee-4276-82b0-9f9b9c362461)

**The Output matches all the required  design values.** <br>
This shows two MOSFETS working in the saturation. 
VGS > VTH & VDS > VOV<br>
**VGS = 1.2-0.399 = 0.801V > 0.366V(VTH),** <br>
**VDS = 1.25-0.4 = 0.85V > (0.8-.366)V = 0.85 > 0.434V (VOV).** <br>

#### 2. TRANSIENT ANALYSIS
Follow the same steps to perform Transient Analysis.

![image](https://github.com/user-attachments/assets/5e381807-dcad-497a-9acf-60fb99fecaa9)


The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>

The Practical Gain = **VOUTpp/VINpp** . <br>
AV = -124.8135mV/100mV = **-1.248 V/V**. <br>

Gain in db scale:-
Av = **20*log(Voutpp/Vinpp).** <br>
Av = **1.924 db**. <br> 

#### DIFFERENTIAL GAIN:-

![image](https://github.com/user-attachments/assets/87531d4a-433b-494f-987a-6a4fd0722386)


From the graph The Differential Gain = -250mV/100mV = **-2.5 V/V**.<br>
Gain in db scale is = 20*log(Votpp/vinpp) = 7.9588 V/V.<br>

#### 3. AC ANALYSIS
Follow the same steps to perform AC Analysis.

![image](https://github.com/user-attachments/assets/0ef1dbf0-9521-4cbc-8393-1aeb1e2c6684)


From the above graph we can get the **Band-Width & Gain** of the circuit.<br>
The Band Width of the Circuit is **33.115 GHz & 1.9db**

