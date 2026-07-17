# PID Autotuning for a Closed-Loop DC-DC Buck Converter Using MATLAB/Simulink

## Overview

This project demonstrates the design, modeling, PID autotuning, and implementation of a closed-loop DC-DC Buck Converter in MATLAB/Simulink. Instead of directly tuning the physical converter, an equivalent transfer function model was first derived from the converter parameters. The PID controller was autotuned using this mathematical model, and the optimized controller gains were then implemented in the actual switching converter to achieve accurate voltage regulation.

---

## Workflow

The complete design procedure followed in this project is:

1. Selected the Buck Converter circuit parameters (R, L, and C).
2. Derived the small-signal transfer function of the converter using the circuit parameters.
3. Built an equivalent transfer function model in MATLAB/Simulink.
4. Performed PID controller autotuning using MATLAB PID Tuner.
5. Obtained the optimized PID gains.
6. Applied the tuned PID coefficients to the actual closed-loop switching Buck Converter.
7. Verified the output voltage and current through simulation.

---

## System Specifications

| Parameter | Value |
|----------|------:|
| Input Voltage | 12 V |
| Reference Voltage | 5 V |
| Output Voltage | 4.99 V |
| Output Current | 2 A |
| PWM Switching Frequency | 400 kHz |
| Controller | PID |
| Tuning Method | MATLAB PID Autotuner |

---

## Controller Design

The controller was designed using an equivalent transfer function model derived from the Buck Converter's passive components.

### Design Steps

- Derive converter transfer function from RLC values.
- Construct the transfer function model in Simulink.
- Tune the PID controller using MATLAB PID Tuner.
- Export the optimized PID gains.
- Replace the initial PID gains in the switching converter with the tuned values.
- Simulate the complete closed-loop converter.

This approach significantly reduces trial-and-error tuning while improving transient response and steady-state accuracy.

---

## Simulation Results

The closed-loop Buck Converter successfully regulated the output voltage close to the desired reference.

### Performance

- Input Voltage: **12 V**
- Desired Output Voltage: **5 V**
- Obtained Output Voltage: **4.99 V**
- Output Current: **2 A**
- PWM Frequency: **400 kHz**

The output voltage closely tracks the reference with negligible steady-state error. The voltage response settles smoothly around **5 V** with minimal overshoot and ripple.

---

## Repository Structure

```
.
├── Buck_Converter_PID_Autotuning.slx      # Complete Simulink model
├── README.md
└── Results/
    ├── All Parameters.png                 # Converter design parameters
    ├── Circuit Used.png                   # Buck converter circuit schematic
    ├── Equivalent TF Model.png            # Transfer function model in Simulink
    ├── PWM Generator Specs.png            # PWM generator configuration (400 kHz)
    ├── Values of PID Coefficients.png     # Tuned PID gains
    ├── Step Plot (Reference vs Output).png# PID tuning response
    ├── Blue Output Voltage.png            # Output voltage waveform
    └── Yellow Output Voltage.png          # Output voltage comparison waveform
```

### Repository Contents

- **Buck_Converter_PID_Autotuning.slx** – Complete MATLAB/Simulink model containing:
  - Buck converter power circuit
  - Transfer function model derived from the converter parameters
  - PID autotuning using MATLAB PID Tuner
  - Closed-loop implementation with tuned PID gains
  - Voltage and current measurement blocks

- **Results/** – Images documenting the complete design and simulation process, including:
  - Circuit schematic
  - Design parameters
  - Transfer function model
  - PWM generator specifications
  - Optimized PID coefficients
  - Step response obtained during autotuning
  - Output voltage waveforms and simulation results

---

## Software Used

- MATLAB R2026a
- Simulink
- Simscape Electrical
- PID Controller Toolbox

---

## Key Features

- Mathematical modeling using transfer function
- PID autotuning using MATLAB PID Tuner
- Closed-loop voltage regulation
- High-frequency PWM switching (400 kHz)
- Accurate voltage tracking
- Modular Simulink implementation

---

## Results Summary

| Parameter | Expected | Obtained |
|-----------|----------|---------:|
| Output Voltage | 5.00 V | 4.99 V |
| Output Current | 2 A | 2 A |
| Voltage Regulation | Excellent | ✓ |
| Steady-State Error | 0 V | ≈0.01 V |

---

## Future Improvements

- Implement PI, FOPID, and Adaptive PID controllers.
- Compare PID with Sliding Mode Control (SMC).
- Analyze line and load regulation.
- Evaluate efficiency under varying load conditions.
- Deploy the controller on embedded hardware for real-time implementation.

---

## Author

**Ashutosh Biswal**

Electrical Engineering
