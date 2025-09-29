# Hybrid and Embedded Control Systems – Homework 1

This repository contains solutions and simulations for **Homework 1** of the course *EL2450: Hybrid and Embedded Control Systems* at KTH. The homework introduces the fundamentals of **digital control design**, using a **double-tank system** as the controlled process.

## Project Overview

* **Course:** EL2450 – Hybrid and Embedded Control Systems
* **Assignment Date:** January 2025
* **Main Topics:**

  * Modeling of a coupled double-tank system
  * Continuous-time control design using PID (pole placement)
  * Discretization and digital implementation of controllers
  * State-space modeling and observer-based control design
  * Effects of quantization in digital control systems

## Assignment Structure

### Part 1 – System Modeling

* Nonlinear differential equations for water levels in the two tanks.
* Linearization and derivation of transfer functions.

### Part 2 – Continuous Control Design

* Design of PID controller via **pole placement**.
* Simulation of closed-loop performance against rise time, overshoot, and settling-time requirements.
* Evaluation of control performance under different pole placements.

### Part 3 – Digital Control Design

* Discretization of continuous controller (`c2d` with ZOH).
* Analysis of sampling time influence on stability and performance.
* State-space discretization and design of observer-based controller.
* Verification of **separation principle** and pole placement in discrete-time.

### Part 4 – Quantization

* Simulation of quantization effects in A/D and D/A conversion.
* Implementation of quantization with saturation in Simulink.
* Analysis of control degradation with different quantization levels.

## Repository Structure

```
.
├── models/
│   ├── tanks.mdl                # Simulink model of coupled tanks
│   ├── controllers.mdl          # Continuous and discrete controllers
│   ├── custom_blocks/           # Quantizer with saturation
│
├── scripts/
│   ├── control_design.m         # Controller design and parameter setup
│   ├── polePlacePID.m           # PID parameter computation
│
├── results/
│   ├── simulations/             # Step responses and stability plots
│   ├── quantization/            # Performance degradation plots
│
├── report/
│   └── Homework1_EL2450.pdf
│
└── README.md
```

## Usage Instructions

### Requirements

* MATLAB/Simulink

### Running the Simulations

1. Open the `tanks.mdl` Simulink model.
2. Connect controllers from `controllers.mdl`.
3. Run simulations with different parameter settings (χ, ζ, ω₀).
4. For digital control, discretize the designed controller using:

   ```matlab
   c2d(F, Ts, 'ZOH')
   ```
5. Add quantization blocks to analyze the effect of limited resolution.

---

📄 This repository contains MATLAB/Simulink code, analysis, and report for Homework 1, focusing on continuous and digital control design of a double-tank system.
