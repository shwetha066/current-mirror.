
# 🔥 Experiment 6 — Current Mirror Design and Analysis

## 🎯 Objective

- To design a current mirror circuit serving as an active load.
- Specifications:
  - Gain (A_v) > -10 V/V
  - V_DD = 1.8V
  - Power ≤ 1mW
- Extend the design into a differential amplifier using the current mirror and perform:
  - DC analysis
  - Transient analysis
  - AC analysis

## 📚 Theory

A **current mirror** is a fundamental analog circuit that replicates a reference current (I_REF) to produce one or more copies.  
It ensures constant current regardless of variations in load or supply voltage.

- **Ideal Current Mirror Relation**:
  I_copy = N × I_REF
- **Applications**:
  - Biasing amplifiers
  - Signal conditioning
  - Analog IC design

## ⚙️ Design Calculations

- **Total Current (I)**:
  I = 1mW / 1.8V = 0.555 mA

### ➡️ Case 1: 1:1 Current Ratio
- I_ref = I_out = 0.277 mA

### ➡️ Case 2: 1:2 Current Ratio
- I_ref = 0.1851 mA
- I_out = 0.3703 mA

## 🛠️ Simulation Setup

| Parameter | Setting |
|:---------:|:-------:|
| Supply Voltage | ±1.8V |
| Input Signal (AC) | Sine wave, 1 kHz |
| Analysis Types | DC, Transient, AC |

## 📈 Results

### Case Studies

| Length | Ratio | Gain (V/V) | Bandwidth (MHz) |
|:------:|:-----:|:----------:|:---------------:|
| 180 nm | 1:1   | 9.67       | 886.2           |
| 500 nm | 1:1   | 11.95      | 1699            |
| 1 µm   | 1:1   | 9.45       | 1029            |
| 180 nm | 1:2   | 11.7       | 398.8           |
| 500 nm | 1:2   | 9.95       | 1027            |
| 1 µm   | 1:2   | 11.3       | 656.2           |

## 🔍 Differential Amplifier Using Current Mirror

| Parameter | Value |
|:---------:|:-----:|
| Gain      | -25.56 V/V |
| Bandwidth | 745.42 MHz |

## 📝 Inference

- **Current mirror improves amplifier stability and gain.**
- **Practical deviations** in W/L ratios are due to channel length modulation, threshold voltage variation, and body effect.
- **Cascoded current mirrors** are recommended for better output resistance and gain.

# ✅ Experiment Completed

# 📂 Recommended Folder Structure

```
Current-Mirror-Experiment/
│
├── README.md
├── Circuit_Diagrams/
│    ├── NMOS_Current_Mirror.png
│    ├── PMOS_Current_Mirror.png
│    └── Differential_Amplifier.png
│
├── Simulation_Files/
│    ├── CurrentMirror.asc
│    └── DifferentialAmplifier.asc
│
├── Results/
│    ├── DC_Analysis.png
│    ├── AC_Analysis.png
│    └── Transient_Analysis.png
```
