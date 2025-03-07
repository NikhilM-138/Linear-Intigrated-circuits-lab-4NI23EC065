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
![image](https://github.com/user-attachments/assets/a10e8261-e306-489c-98cf-f32345fb06e8)<br>

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

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.

![image](https://github.com/user-attachments/assets/803a5d72-a341-4064-8358-e0a831032d10)

For Applying the Amplitude of the input signal should be **vgs<<2VOV**.
vgs<<2*(VGS-VTH). <br>
vgs<<

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
Now select the type of sweep as **Decade** , No.of points as **10m** and then give **Starting frequency as 1Hz & Ending as 1MHz** then Run.<br>
![image](https://github.com/user-attachments/assets/b107632e-ced1-4122-b95e-3ab1c54e97c1) <br>

From the above graph we can get the **Band-Width** of the circuit.<br>
The Band Width of the Circuit is **2.42 MHz**.

#### 4.Varriying the VICM VOLAGE.
First we are finding the range of the VICM.<br>
**VICM(min) = VTH + VP**.<br>
VICM(min) = 0.366+0.4 .<br>
**VICM(min) = 0.766 V**.<br>

**VICM(max) = VOCM + VTH**. <br>
VICM(max) = 1.25+0.366 .<br>
**VICM(max) = 1.616 V**.<br>

**Giving the input as VICM(min):-**
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
![image](https://github.com/user-attachments/assets/b1a9e0a2-5851-4d28-84a8-4950854f1ed2)


Gain is = -289.23m/100m = **-2.8923 V/V**
The gain has been reduced -2.893 V/V .
##### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/2859f9fa-2185-439d-8cae-63394a10e961)

The Bandwith has increased to **56.6MHZ** .<br>

**Giving the input as VICM(max):-**
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
##### 2.TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/eb74afdd-2aeb-469e-b71d-cbee90ba0c02)

Gain is = -65.3m/100m = **-0.653 V/V**.<br>
The gain has been reduced -0.653 V/V .
##### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/369df8df-d34f-4f5a-a346-04dbc11ea016)

### 6.SIMULATION OF MOS DIFFERENTIAL AMPLIFIER WITH CONSTANT CURRENT SOURCE IN PLACE OF SOURCE RESISTOR (Rss)
#### 1.DC ANALYSIS

![image](https://github.com/user-attachments/assets/d4aff175-f4bd-431f-9fa1-7f8088d7990c)


