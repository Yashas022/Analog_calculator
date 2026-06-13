# ECG Analog Calculator Circuit for Biomedical Signal Processing




### Design and Implementation of an Op-Amp Based Analog Computational Circuit for ECG Biomedical Signal Processing and Time-Frequency Domain Analysis

**NIE Student Research Symposium 2026**


</div>

---

##  Overview

Electrocardiogram (ECG) signals are low-amplitude biomedical signals that are highly susceptible to noise, baseline drift, motion artifacts, and power-line interference. This project presents the design and implementation of an **Op-Amp Based Analog Calculator Circuit** that performs signal conditioning using analog computational operations.

The system amplifies, filters, averages, integrates, and compresses ECG signals to improve signal quality while preserving clinically relevant information.

---

##  Objectives

- Generate a realistic ECG signal with P-QRS-T morphology.
- Amplify weak ECG signals using an instrumentation amplifier.
- Remove baseline wander and DC drift.
- Suppress high-frequency noise and 50 Hz power-line interference.
- Implement analog mathematical operations:
  - Addition
  - Averaging
  - Integration
  - Logarithmic Compression
- Analyze signals in time and frequency domains.
- Validate performance using MATLAB Simulink and LTspice.

---

##  Problem Statement

Raw ECG signals have amplitudes in the range of **0.5 mV to 5 mV** and are often corrupted by:

- 50 Hz mains interference
- Baseline wander
- Motion artifacts
- Muscle noise (EMG)
- Electrode contact noise

These disturbances can mask important ECG features such as:

- P Wave
- QRS Complex
- T Wave

The goal is to develop a low-cost analog front-end capable of conditioning ECG signals for reliable biomedical analysis.

---

## System Architecture

```text
                ECG Signal
                     │
                     ▼
      Instrumentation Amplifier (IA)
                     │
                     ▼
        High Pass Filter (0.5 Hz)
                     │
                     ▼
         Low Pass Filter (~40 Hz)
                     │
                     ▼
           50 Hz Notch Filter
                     │
                     ▼
            Summing Amplifier
                     │
                     ▼
                Integrator
                     │
                     ▼
          Logarithmic Compressor
                     │
                     ▼
            Conditioned ECG Output
```

---

##  Working Principle

### Stage 1: Instrumentation Amplifier

- High input impedance
- Amplifies low-amplitude ECG signals
- Provides initial signal conditioning

**Output Node:** `ecg_ia`

---

### Stage 2: Signal Conditioning Filters

#### High Pass Filter (HPF)

- Cutoff Frequency: 0.5 Hz
- Removes baseline wander
- Eliminates DC drift

**Output Node:** `ecg_hpf`

#### Low Pass Filter (LPF)

- Cutoff Frequency: ~40 Hz
- Removes high-frequency noise
- Performs weighted averaging

**Output Node:** `ecg_lpf`

#### Notch Filter

- Center Frequency: 50 Hz
- Removes mains interference

**Output Node:** `ecg_notch`

---

### Stage 3: Analog Calculator Operations

#### Summing Amplifier

Performs signal addition.

**Output Node:** `ecg_sum`

#### Integrator

Performs continuous-time averaging and smoothing.

**Output Node:** `ecg_int`

#### Logarithmic Compressor

Compresses signal dynamic range.

**Output Node:** `ecg_log`

---

##  Mathematical Operations Implemented

| Operation | Circuit Block |
|------------|---------------|
| Addition | Summing Amplifier |
| Averaging | LPF + Integrator |
| Amplification | Instrumentation Amplifier |
| Compression | Log Amplifier |

---

## 🔩 Hardware Components

### Active Components

| Component | Quantity |
|------------|------------|
| LM358 Dual Op-Amp | 5 |
| 1N4148 Diode | 1 |

### Passive Components

| Component | Value |
|------------|------------|
| Resistors | 1 kΩ, 10 kΩ, 33 kΩ, 4.7 kΩ |
| Capacitors | 10 µF, 1 µF, 100 nF |
| LED Resistor | 470 Ω |

### Power Supply

```text
+9V
 │
 ├── Circuit
 │
GND
 │
 ├── Circuit
 │
-9V
```

---

##  Software Tools

### MATLAB

Used for:

- ECG generation
- Signal analysis
- FFT computation
- PSD analysis

### Simulink

Used for:

- System-level modeling
- Time-domain simulation
- Frequency-domain verification

### LTspice

Used for:

- Circuit simulation
- Component-level validation
- Non-ideal behavior analysis

---

##  Performance Results

### Signal-to-Noise Ratio (SNR)

| Stage | SNR |
|---------|---------|
| Input Signal | 31 dB |
| HPF Output | 32 dB |
| LPF Output | 44 dB |
| Notch Output | 52 dB |
| Integrator Output | 59 dB |
| Final Output | 64 dB |

### Overall Improvement

```text
Input SNR   : 31 dB
Output SNR  : 64 dB

Improvement : +34 dB
```

---

##  Time Domain Analysis

The conditioned ECG signal exhibits:

- Reduced baseline drift
- Improved waveform clarity
- Preserved P-QRS-T morphology
- Stable output amplitude

---

##  Frequency Domain Analysis

The system successfully:

- Removes low-frequency baseline wander
- Suppresses 50 Hz interference
- Reduces high-frequency noise
- Preserves ECG diagnostic bandwidth

### Diagnostic Band

```text
0.5 Hz  ───────────────────► 40 Hz
```

---

##  Socio-Economic Impact

### Healthcare Accessibility

- Conventional ECG Machines:
  - ₹50,000 – ₹5,00,000

- Proposed Analog Front-End:
  - Less than ₹500

### Benefits

- Rural healthcare support
- Low-cost cardiac screening
- Educational biomedical toolkit
- Indigenous medical device development

---

##  Future Scope

### Hardware Improvements

- INA128 Instrumentation Amplifier
- AD8221 Precision Front-End
- PCB Implementation
- Driven Right Leg (DRL) Circuit

### Digital Integration

- ADC Interface
- Bluetooth Connectivity
- Smartphone Monitoring

### AI Applications

- Arrhythmia Detection
- Machine Learning Classification
- Real-Time Cardiac Monitoring

---



##  Team PQRST SMASHERS

| Name | Department |
|--------|------------|
| Vasundhara B N | ECE |
| Yashas H D | ECE |
| Shreevathsa K S | ECE |
| Vijeth D S | ECE |

---

