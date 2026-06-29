# Two-Stage-Op-Amp-Design-Miller-Feedforward-Nested-Miller-Compensation-
# Two-Stage CMOS Operational Amplifier Compensation Techniques

A comparative study of three frequency compensation techniques for high-performance CMOS operational amplifiers designed using the **SCL 180 nm CMOS PDK** in **Cadence Virtuoso (Spectre)**.

The project investigates the impact of different compensation schemes on gain, bandwidth, phase margin, transient response, and process-corner robustness.

---

## Project Overview

Three amplifier architectures were designed and simulated:

- **Miller Compensation**
- **Feedforward Compensation**
- **Nested Miller Compensation (NMC)**

Each topology was analyzed for:

- Open-loop gain
- Unity-Gain Bandwidth (UGB)
- Phase Margin (PM)
- CMRR
- Output swing
- Power consumption
- Process corner performance (TT, FF, SS, SF, FS)
- Step response
- Stability with different feedback factors

---

## Design Specifications

| Parameter | Miller | Feedforward | Nested Miller |
|------------|--------:|------------:|--------------:|
| Technology | SCL 180 nm CMOS | SCL 180 nm CMOS | SCL 180 nm CMOS |
| Supply Voltage | 1.8 V | 1.8 V | 1.8 V |
| Load Capacitance | 1 pF | 1 pF | 1 pF |

---

# Compensation Techniques

## 1. Miller Compensation

- Folded-Cascode OTA as first stage
- Common-Source second stage
- Miller capacitor with nulling resistor
- Pole-splitting compensation

### TT Corner Performance

| Metric | Value |
|---------|------:|
| DC Gain | **131 dB** |
| CMRR | **177 dB** |
| UGB | **10 MHz** |
| Phase Margin | **60°** |
| Output Swing | **1.02 V** |

### Advantages

- Simple implementation
- Excellent gain
- Predictable behavior
- Good output swing

### Limitations

- Right-half-plane zero
- Limited bandwidth
- Requires nulling resistor

---

## 2. Feedforward Compensation

A feedforward OTA provides a high-frequency path that introduces a Left-Half-Plane (LHP) zero instead of the RHP zero found in Miller compensation.

### TT Corner Performance

| Metric | Value |
|---------|------:|
| DC Gain | **134 dB** |
| CMRR | **150 dB** |
| UGB | **201 MHz** |
| Phase Margin | **54.5°** |
| Output Swing | **1.04 V** |

### Advantages

- Extremely high bandwidth
- No Miller capacitor
- No nulling resistor
- LHP zero improves phase response

### Limitations

- More sensitive to bias shifts
- Output swing degrades at some process corners

---

## 3. Nested Miller Compensation

A three-stage architecture employing two nested Miller compensation loops to achieve ultra-high gain.

### TT Corner Performance

| Metric | Value |
|---------|------:|
| DC Gain | **242 dB** |
| CMRR | **260 dB** |
| UGB | **5.09 MHz** |
| Phase Margin | **68°** |
| Output Swing | **1.01 V** |
| Power | **0.583 mW** |

### Advantages

- Extremely high gain
- Excellent stability
- High CMRR
- Low power

### Limitations

- Complex architecture
- Sensitive inter-stage biasing
- Requires careful common-mode control

---

# Comparison

| Feature | Miller | Feedforward | Nested Miller |
|----------|--------|-------------|---------------|
| DC Gain | High | High | Very High |
| Bandwidth | Medium | Very High | Low |
| Stability | Good | Moderate | Excellent |
| Design Complexity | Low | Medium | High |
| RHP Zero | Yes | No | Yes |
| Best Use Case | General-purpose Op-Amps | High-speed analog circuits | Precision high-gain amplifiers |

---

# Software Used

- Cadence Virtuoso
- Spectre Simulator
- SCL 180 nm CMOS PDK

---

# Simulations Performed

- Open-loop AC analysis
- Phase Margin extraction
- CMRR analysis
- Output swing analysis
- Process corner simulations
- Transient step response
- Feedback factor (β) analysis

---

# Key Results

- Achieved **242 dB** maximum open-loop gain using Nested Miller Compensation.
- Achieved **201 MHz** unity-gain bandwidth using Feedforward Compensation.
- Demonstrated trade-offs among gain, bandwidth, stability, and robustness.
- Evaluated all topologies under multiple process corners.

---

# Repository Structure

```
├── Report.pdf
├── Schematics/
├── Symbols/
├── Simulation/
│   ├── AC
│   ├── Transient
│   ├── Corners
│   └── Outputs
├── Images/
└── README.md
```

---

# References

1. P. E. Allen and D. R. Holberg, *CMOS Analog Circuit Design*, 3rd Edition.
2. Behzad Razavi, *Design of Analog CMOS Integrated Circuits*, 2nd Edition.
3. W. Sansen, *Analog Design Essentials*.

---

## Author

**Raj Patel**

Electrical Engineering  
Indian Institute of Technology Gandhinagar
