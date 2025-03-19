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

  
