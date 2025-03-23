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
