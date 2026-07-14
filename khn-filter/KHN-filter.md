# KHN State-Variable Audio Filter

**Co-authors:** Pranshu Sabat, Aditi Pore, Roshan Powar — Dept. of Electronics and Telecommunication Engineering, COEP Technological University
**Guide:** Dr. Deeplaxmi Niture
**Tools:** TL071 Op-Amps, Proteus (simulation + Bode/step response analysis), RIGOL DSO

## Overview

A second-order Kerwin-Huelsman-Newcomb (KHN) active filter built around a 1 kHz center frequency, producing simultaneous Low-Pass, Band-Pass, and High-Pass outputs from a single circuit — a low-cost analog alternative to DSP-based filtering in active noise cancellation (ANC) systems.

## Architecture

The KHN topology uses three op-amps in a state-variable configuration:

1. **Summing Amplifier** — combines the input signal with feedback from the BP and LP outputs to generate the High-Pass output
2. **First Integrator** — integrates the HP signal to produce the Band-Pass output
3. **Second Integrator** — integrates the BP signal to produce the Low-Pass output

Feedback from the BP and LP stages back into the summing amplifier establishes the overall second-order behavior — this is what allows all three filter responses to emerge from one shared circuit rather than three separate filter designs.

## Design Calculations

Center frequency is set by the integrator RC time constant:

f₀ = 1 / (2πRC)

With R = 16 kΩ and C = 10 nF: **f₀ ≈ 995 Hz ≈ 1 kHz**

Equal resistor values in the summing stage maintain unity gain and a Butterworth-characteristic response; the quality factor Q is independently adjustable via resistor ratios.

## Simulation Results (Proteus)

- **120 Hz:** LPF output dominant, HPF flat, BPF negligible — confirms correct low-frequency rolloff
- **1 kHz (center frequency):** All three outputs (LPF, BPF, HPF) present as clean sine waves — the defining behavior of the state-variable topology at resonance
- **4 kHz:** HPF dominant, BPF/LPF suppressed — confirms correct high-frequency response
- **Bode plot:** LPF flat at 0 dB up to ~500 Hz then rolls off at −40 dB/decade (2nd order); HPF mirrors this in reverse; BPF peaks near 1 kHz at ≈−7 dB (~0.45× gain), consistent with a single integrated BP node rather than a dedicated resonator
- **Step response:** Confirms expected transient behavior — HPF shows sharp edge spikes only, LPF/BPF show settling transients consistent with second-order dynamics

## Hardware Validation

Implemented first on breadboard, then transferred to a soldered zero-PCB board for reliability. DSO measurements at 120 Hz, 1 kHz, and 4 kHz closely matched Proteus simulation results:

| Frequency | LPF Output | BPF Output | HPF Output |
|---|---|---|---|
| 120 Hz | 5.58 V | 850 mV | 126 mV |
| 1 kHz | 2 V | 2.5 V | 2.75 V |
| 4 kHz | 300 mV | 1.4 V | 5.19 V |

Minor deviations between simulation and hardware are attributed to resistor tolerances and op-amp non-idealities — expected and within acceptable bounds.

## Applications

Audio equalizers, music synthesizers, biomedical signal conditioning, analog signal processing lab experiments, and low-cost ANC systems where a full DSP pipeline isn't justified.

## Key Takeaway

This project demonstrates a complete analog design workflow — theoretical derivation → circuit design → Proteus simulation (frequency response, Bode, step response) → breadboard build → hardware validation via DSO — with simulation and hardware results in close agreement at all three test frequencies.
