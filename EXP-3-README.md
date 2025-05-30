## EXPAERIMENT NO.3
# CURRENT MIRRORING CIRCUITS
### 1.INTRODUCTION
A current mirror circuit is a fundamental building block in analog electronics, primarily used for current replication and biasing applications. It ensures that the output current closely follows a reference current, making it useful in integrated circuits (ICs), amplifiers, and active loads. Current mirrors are widely used due to their high output resistance, improved accuracy, and ability to maintain constant current independent of voltage variations. The experiment involves simulating different types of current mirror circuits, such as basic current mirrors, Wilson current mirrors, and cascode current mirrors, to analyze their performance, current transfer accuracy, and voltage dependencies. By understanding these circuits, engineers can design efficient current sources and biasing networks for various analog and mixed-signal applications.

![main-qimg-8a117802691bf82b823020d9620d8148-pjlq](https://github.com/user-attachments/assets/a1949a00-ef8f-4ab6-8d78-123f4da7b1db)

### 2.AIM OF THE EXPERIMENT
The objective of this experiment is to **design, analyze, and simulate a current mirror circuit used as a load in an amplifier** to evaluate its performance characteristics. The experiment focuses on:
**1. Designing Current Mirror Circuits**
- Implementing a **basic current mirror** with a **1:1 current ratio**.
- Analyzing the impact of **device dimensions (W/L ratios)** on current mirroring accuracy.
- Extending the design for **1:2 current mirroring** to observe scaling effects.

**2. Performance Analysis**
- Conducting **DC analysis** to evaluate current transfer accuracy.
- Performing **AC analysis** to determine the frequency response and stability.
- Measuring the **maximum output voltage swing** in transient simulations.

**3. Integration with a Differential Amplifier**
- Replacing passive resistive loads with an **active current mirror load**.
- Comparing performance with conventional resistor-loaded differential amplifiers.
- Investigating **gain improvement and common-mode rejection** in the modified design.

**4. Simulation, Current Mirror Ratio Variation, and Analysis**
- Using **LTspice** to simulate circuit behavior.
- Evaluating the impact of **channel length variation (Lmin = 180nm, L = 500nm, L = 1µm)** on performance.
- Varying the **current mirror ratio** and analyzing its effect on circuit performance.
- Studying the impact of current mirroring on **gain, stability, and output swing**.

 #### DESIGN QUSETION
 <img src="https://github.com/user-attachments/assets/06ca76d9-8dbe-4f3c-bf0d-8adf5344aa02" width="500">

 <img src="https://github.com/user-attachments/assets/54b45a24-683d-4ac3-b220-f6ab146bb944" width="500">

### 4. ANALYTICAL DESIGN APPROACH
GIVEN:<br>
VDD = 1.8V <br>
P <= 1mW <br>
AV > -10v/v <br>

ITOTAL = P/VDD <br>
ITOTAL <= 1/1.8 <br>
ITOTAL <= 0.555mA <br>

ITOTAL = IREF + IX <br>
For **1:1 Current mirror ratio. IREF = 0.277mA & IX = 0.277mA** <br>
For **1:2 Current mirror ratio IREF is 0.185mA & IX = 0.365mA** <br>

**THE ASPECT RATIO'S OF MOSFET IS 16.66**<br>

**THE ASPECT RATIO'S OF MOSFET FOR 1:1 CURRENT MIRROR**:<br>
  - M1 = 3um/180nm
  - M2 = 3um/180nm
  - M3 = 3um/180nm
**VGS = 0.838V**<br>

**THE ASPECT RATIO'S OF MOSFET FOR 1:2 CURRENT MIRROR**:<br>
  - M1 = 3um/180nm
  - M2 = 6um/180nm
  - M3 = 6um/180nm
**VGS = 0.763V**<br>
### 5. SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER OF 1:1 MIRROR RATIO.
#### 1. DC ANALYSIS
Built the circuit as per the circuit diagram below <br>
![image](https://github.com/user-attachments/assets/a0dea230-bf02-4c0a-a8de-d35094477f26)


To perform the DC Analysis click the edit simulation and select the DC OP point(.op).<br>
![image](https://github.com/user-attachments/assets/dd4127da-8e3c-4710-b74f-017639d1210d)


**ID M1 =  277uA , ID M2 = 277.5uA , ID M3 = 277.5uA .** <br>
#### 2.TRANAIENT ANALYSIS 
To perform Transient analysis click the edit Simulation then click on Transient Analysis.<br>
Now give the stop time as 10ms and Run.<br>

![image](https://github.com/user-attachments/assets/12b6c47d-f490-4395-a346-421ca9effbe2)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>

The Gian from The Transient Analysis is -10.1 V/V.
#### 3. AC ANALYSIS
To perform AC Analysis click the edit simulation then click on AC Analysis.<br>
Now select the type of sweep as **Decade** , No.of points as **10m** and then give **Starting frequency as 1Hz & Ending as 1MHz** then Run.<br>

![image](https://github.com/user-attachments/assets/dcb6bc48-a962-4f5b-b354-37e79c4b3d66)

**Gain in db is 22.1db & Bandwidth is 2.29GHz .**

### 6. SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER OF 1:2 MIRROR RATIO.
#### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/3683c9d2-3189-4595-9001-08793225dd39)

Follow the same steps to perform DC Analysis.

![image](https://github.com/user-attachments/assets/607d7b1a-d17d-42ff-8f7d-a1e1b3fd0f8b)

**ID M1 =  185uA , ID M2 = 365.17uA , ID M3 = 365.17uA .** <br>
#### 2.TRANAIENT ANALYSIS
Follow the same steps to perform Transient Analysis.

![image](https://github.com/user-attachments/assets/a5bc3066-6712-4e5f-be58-d15f7e961d0f)
The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>

The Gian from The Transient Analysis is -11.69 V/V.
#### 3. AC ANALYSIS
Follow the same steps to perform AC Analysis.
![image](https://github.com/user-attachments/assets/9de834c1-efea-4407-93df-54240af92add)

**Gain in db is 22.96db & Bandwidth is 1.435GHz .**

### 7. SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER OF 1:3 MIRROR RATIO.
For **1:3 Current mirror ratio IREF is 0.139mA & IX = 0.416mA** <br>
**THE ASPECT RATIO'S OF MOSFET FOR 1:3 CURRENT MIRROR**:<br>
  - M1 = 6um/180nm
  - M2 = 18um/180nm
  - M3 = 18um/180nm
**VGS = 0.632V**<br>

#### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/97529e30-4025-4d4d-8630-bc776836220f)

Follow the same steps to perform DC Analysis.
![image](https://github.com/user-attachments/assets/889356c0-2ce4-43c4-a453-313aaa4326c6)

**ID M1 =  139uA , ID M2 = 416.08uA , ID M3 = 416.08uA .** <br>

#### 2.TRANAIENT ANALYSIS
Follow the same steps to perform Transient Analysis.

![image](https://github.com/user-attachments/assets/25b8d935-8eaa-49c7-826d-f4a5468d0968)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>

The Gian from The Transient Analysis is -14.69 V/V.

#### 3. AC ANALYSIS
Follow the same steps to perform AC Analysis.
![image](https://github.com/user-attachments/assets/9ce3d467-4a91-438f-8168-4af0d0da2e7f)

**Gain in db is 27.3db & Bandwidth is 493.415MHz .**

### 8. SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER OF 1:4 MIRROR RATIO.
For **1:4 Current mirror ratio IREF is 0.111mA & IX = 0.444mA** <br>
**THE ASPECT RATIO'S OF MOSFET FOR 1:4 CURRENT MIRROR**:<br>
  - M1 = 9um/180nm
  - M2 = 36um/180nm
  - M3 = 36um/180nm
**VGS = 0.604V**<br>

#### 1.DC ANALYSIS
![image](https://github.com/user-attachments/assets/0a70a8a5-fd7a-4768-9997-52527a25f20e)


Follow the same steps to perform DC Analysis.
![image](https://github.com/user-attachments/assets/9eedc717-a6c0-4697-b6a5-d1f2456d1052)

**ID M1 = 111uA , ID M2 = 444.39uA , ID M3 = 444.39uA .** <br>

#### 2.TRANAIENT ANALYSIS
Follow the same steps to perform Transient Analysis.

![image](https://github.com/user-attachments/assets/80d9f8c4-8ab0-4e7b-b73e-36512d498bdb)

The above Output shows the Amplified Signal with 180° Phase Shift of input signal of Amplitude 50mV.<br>

The Gian from The Transient Analysis is -15.6 V/V.

#### 3. AC ANALYSIS
Follow the same steps to perform AC Analysis.

![image](https://github.com/user-attachments/assets/823062b0-a8d5-4e91-b536-e9b09b2b0f94)

**Gain in db is 28.4db & Bandwidth is 246.09MHz .**
### 9.VARRIYING L VALUE:
I) L=500nm then w = 8.334um
NOW PERFORMING THE DC ANALYSIS:
![image](https://github.com/user-attachments/assets/1c427742-fd94-46e8-a2f1-e05b63fd679e)

**ID M1 = 82.7mA , ID M2 = 0.768pA , ID M3 = 2.52pA .** <br>

II)L = 1um then W = 16.667u
NOW PERFORMING THE DC ANALYSIS:
![image](https://github.com/user-attachments/assets/4ff29699-6832-478a-a610-bb8d4ad42c1d)

**ID M1 = 167.101mA , ID M2 = 2.74pA , ID M3 = 4.766pA .** <br>

### 10. PART B:DESIGN OF DIFFERENTIAL AMPLIFIER USING CURRENT MIRROR
 The circuit comprises six MOSFETs (M1 to M6) with distinct (W/L) ratios, designed to operate in the **saturation region** to maintain accurate **current mirroring** and **signal amplification**. The aspect ratios of the transistors are carefully chosen to optimize **transconductance (gm), output resistance (ro), and overall circuit stability**.  

- **M1, M2, M3:** **(W/L) = 108μm / 180nm**  
  → These transistors form the **current mirror pair**, ensuring **precise current replication**.  

- **M4:** **(W/L) = 49.1μm / 180nm**  
  → Acts as an **active load**, influencing the **gain** and **linearity** of the circuit.  

- **M5, M6:** **(W/L) = 57.33μm / 180nm**  
  → Function as **differential pair transistors**, determining the circuit's **input impedance** and **common-mode rejection ratio (CMRR)**.  
#### 1.DC ANALYSIS
Built the circuit as per the circuit diagram below <br>
![image](https://github.com/user-attachments/assets/f23ff582-fe6e-46ca-b8d9-4f0cc72899e1)


To perform the DC Analysis click the edit simulation and select the DC OP point(.op).<br>
![image](https://github.com/user-attachments/assets/0babd943-a298-4748-82f0-37c14563c7a0)

#### 2.TRANSIENT ANALYSIS
Follow the same steps to perform Transient
![image](https://github.com/user-attachments/assets/c8a30210-e061-4910-9874-6e302a13eb87)
GAIN is -29.6/20 = 1.45 v/v.
#### 3.AC ANALYSIS
![image](https://github.com/user-attachments/assets/320bad0a-fe17-4608-9d21-bca2e2822ad8)
The Gain is 25.3db.

### 11.RESULT
**Performance Comparision table wrt Current Mirror Ratio:** <br>
| **Current Mirror Ratio** | **IREF (mA)** | **IX (mA)** | **VGS (V)** | **M1 (W/L)** | **M2 (W/L)** | **M3 (W/L)** | **Gain (V/V)** | **Gain (dB)** | **Bandwidth (MHz)** |
|-------------------------|---------------|-------------|-------------|--------------|--------------|--------------|----------------|---------------|---------------------|
| **1:1** | 0.277 | 0.277 | 0.838 | 3µm/180nm | 3µm/180nm | 3µm/180nm | -10.1 | 22.1 | 2290 |
| **1:2** | 0.185 | 0.365 | 0.763 | 3µm/180nm | 6µm/180nm | 6µm/180nm | -11.69 | 22.96 | 1435 |
| **1:3** | 0.139 | 0.416 | 0.632 | 6µm/180nm | 18µm/180nm | 18µm/180nm | -14.69 | 27.3 | 493.4 |
| **1:4** | 0.111 | 0.444 | 0.604 | 9µm/180nm | 36µm/180nm | 36µm/180nm | -15.6 | 28.4 | 246.1 |

---
### 12.INFERENCE


From the experiment and simulations, the following technical inferences can be drawn regarding the **Current Mirror Load Common Source Amplifier** and the **impact of varying the current mirror ratio**:

---

 **1. Impact of Current Mirror Ratio on Gain and Bandwidth**
- As the **current mirror ratio increases**, the **gain increases**, as seen from the values in the comparison table:
  - **1:1 ratio → Gain = -10.1 V/V**
  - **1:2 ratio → Gain = -11.69 V/V**
  - **1:3 ratio → Gain = -14.69 V/V**
  - **1:4 ratio → Gain = -15.6 V/V**
- This happens because a **larger IX (mirrored current) increases the transconductance (gm)**, which directly impacts the voltage gain:
  
  \[
  A_v = -g_m \cdot r_o
  \]

- However, as gain increases, **bandwidth decreases significantly** due to the trade-off between gain and frequency response:
  - **1:1 ratio → Bandwidth = 2290 MHz**
  - **1:2 ratio → Bandwidth = 1435 MHz**
  - **1:3 ratio → Bandwidth = 493.4 MHz**
  - **1:4 ratio → Bandwidth = 246.1 MHz**
- The **higher gain reduces the bandwidth** because increasing the W/L ratio of the MOSFETs **increases capacitance**, which limits high-frequency response.

---

 **2. Voltage Variations and Threshold Effects**
- The **gate-source voltage (VGS) decreases as the current mirror ratio increases**:
  - **1:1 ratio → VGS = 0.838V**
  - **1:2 ratio → VGS = 0.763V**
  - **1:3 ratio → VGS = 0.632V**
  - **1:4 ratio → VGS = 0.604V**
- This happens because, in a current mirror, the MOSFET aspect ratio (W/L) is adjusted to achieve the required current ratio.
- **A lower VGS suggests that the MOSFETs are operating deeper in the saturation region**, which improves current replication accuracy.

---
 **3. Effect of MOSFET Aspect Ratio (W/L)**
- As the **current mirror ratio increases, the W/L ratio of the current mirror transistors (M2, M3) increases significantly**:
  - **1:1 ratio → (M2, M3) = 3µm/180nm**
  - **1:2 ratio → (M2, M3) = 6µm/180nm**
  - **1:3 ratio → (M2, M3) = 18µm/180nm**
  - **1:4 ratio → (M2, M3) = 36µm/180nm**
- Increasing W/L improves current mirroring accuracy but **increases parasitic capacitance**, affecting speed and stability.
- A **larger MOSFET** results in **higher output resistance (r_o)**, which enhances gain but reduces bandwidth.

---

 **4. DC Accuracy and Current Matching**
- From the **DC Analysis**, it is observed that **ID (drain current) values closely match the expected current mirror ratios**:
  - Example for **1:2 ratio**:  
    - **IREF = 185 µA**, **IX (mirrored current) = 365 µA**, which is very close to the expected 1:2 ratio.
  - Example for **1:3 ratio**:  
    - **IREF = 139 µA**, **IX = 416 µA**, which is also accurate.
- This confirms that the **current mirror circuit effectively replicates the reference current**, proving its reliability in biasing applications.

---

 **5. Trade-offs Between Gain, Bandwidth, and Stability**
- **Higher current mirror ratios provide more gain** but reduce bandwidth.
- **Large W/L ratios enhance current mirroring accuracy** but introduce **higher parasitic capacitance**, affecting **high-frequency performance**.
- The circuit shows **180° phase shift**, as expected for a **common-source amplifier with active load**.
- For applications requiring **higher bandwidth (e.g., RF amplifiers)**, a **lower current mirror ratio (1:1 or 1:2) is preferable**.
- For applications needing **high gain (e.g., precision analog circuits)**, a **higher current mirror ratio (1:3 or 1:4) is beneficial**.

---
**6.Gain and Bandwidth Are Lower in Differential Mode**
 - In differential mode, both gain and bandwidth are typically lower compared to single-ended operation due to the way signals are processed and shared between transistors. Since the amplifier responds only to the difference between two input signals, each transistor receives only half of the total signal, effectively reducing the gain. Additionally, the load is shared between both transistors, further decreasing the overall amplification. Bandwidth reduction occurs due to increased parasitic capacitances introduced by current mirror loads and common-mode rejection circuits, which limit high-frequency performance. Moreover, the input capacitance is effectively doubled in differential mode, leading to a lower bandwidth compared to single-ended operation. These factors create a trade-off where differential amplifiers provide better noise immunity and rejection of common-mode signals but at the cost of reduced gain and bandwidth.

---
**7.Effect of Changing L Value in a Current Mirror**

- In a current mirror circuit, the length (L) of the MOSFET channel plays a crucial role in determining the device characteristics. When the L value is changed, it affects the output current due to variations in channel resistance and output conductance. A longer channel length (higher L) increases channel resistance, reducing short-channel effects and improving output resistance, which helps maintain a more stable current. Conversely, a shorter channel length (lower L) results in increased channel modulation, causing greater variations in output current due to drain voltage changes. This explains why modifying the L value alters the mirrored current, impacting the circuit's performance and accuracy.
---
### 13. **Conclusion**
- The experiment **successfully demonstrates how varying the current mirror ratio impacts the performance of an amplifier**.
- **Current mirror loads provide significant gain enhancement over resistive loads**, making them ideal for **differential amplifiers and operational amplifiers**.
- **A balance between gain and bandwidth must be considered** based on circuit requirements.
- The **results validate theoretical expectations**, confirming the accuracy and efficiency of current mirrors in analog design.

---

