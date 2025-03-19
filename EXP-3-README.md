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
I am fixing **IREF = 100uA.** <br>
For **1:1 Current mirror ratio IX is 100uA. ITOTAL = 0.2mA < 0.55mA** <br>
For **1:2 Current mirror ratio IX is 200uA. ITOTAL = 0.3mA < 0.55mA** <br>

### 5. SIMULATION OF CURRENT MIRROR LOAD COMMON SOURCE AMPLIFIER.
#### 1. DC ANALYSIS
Built the circuit as per the circuit diagram below <br>


To perform the DC Analysis click the edit simulation and select the DC OP point(.op).<br>
