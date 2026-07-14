# Seven-Stage Analog EMG Signal Processing Circuit

**Co-authors:** Pranshu Sabat, Aditi Pore, Sajal Patil — Dept. of Electronics and Telecommunication Engineering, COEP Technological University
**Tools:** TL071 Op-Amps, Proteus (KiCad schematic), RIGOL Digital Storage Oscilloscope
**Domain:** Biomedical signal processing, prosthetic control

## Overview

A fully analog, microcontroller-free signal chain that takes weak surface EMG (sEMG) signals (50 µV – 5 mV at the skin) and conditions them into a clean 0–5 V DC envelope suitable for direct prosthetic motor control. Built entirely from TL071 JFET-input op-amps, powered from a dual ±9 V battery supply for a floating, mains-isolated system.

## Why this is hard

sEMG signals present three core challenges: extremely low amplitude (requiring 1,000–10,000× gain), large common-mode interference from 50 Hz mains coupling, and low-frequency motion artefacts below 20 Hz. A usable front-end needs high gain, high CMRR (≥80 dB), and a well-defined 10–500 Hz passband — all without introducing offset or instability.

## Signal Chain (7 Stages)

1. **Instrumentation Amplifier** — 3-op-amp topology, gain = 201 V/V, high input impedance, strong common-mode rejection
2. **High-Pass Filter** — removes DC offset and motion artefacts (target 16 Hz, measured 29.94 Hz)
3. **Low-Pass Filter** — limits bandwidth to reject high-frequency noise (target 480 Hz, measured 431 Hz)
4. **Twin-T Notch Filter** — rejects 50 Hz power-line interference specific to Indian mains supply
5. **Second Gain Stage** — restores signal level after filtering losses, gain = 16 V/V
6. **Precision Full-Wave Rectifier** — uses diodes inside the op-amp feedback loop to eliminate the ~0.6 V diode dead-band at millivolt signal levels
7. **Envelope Detector** — RC low-pass (τ ≈ 1s) smooths the rectified signal into a proportional DC envelope

## Measured Results

| Stage | Target | Measured |
|---|---|---|
| INA Gain | 201 V/V | 201 V/V |
| HPF cutoff | 16 Hz | 29.94 Hz |
| LPF cutoff | 480 Hz | 431 Hz |
| Notch frequency | 50 Hz | 50 Hz |
| Overall gain | — | ≈10,000 V/V |
| CMRR | ≥80 dB | >80 dB |
| Envelope output | 0–5 V | ≈4.92 V (full excitation) |

Small deviations in cutoff frequencies are attributable to standard ±5% component tolerances and remain within acceptable ranges recommended in EMG acquisition literature.

## Validation

Each stage was independently verified on a breadboard prototype using a function generator as input and a digital storage oscilloscope to capture waveforms — confirming instrumentation amplifier gain, filter roll-offs, notch rejection, rectifier behavior (no dead-band), and final envelope tracking from ~30 mV (rest) to ~4.92 V (full contraction).

## Key Design Decision

The entire system is deliberately microcontroller-free — a design choice that trades the flexibility of digital post-processing (used in research-grade multichannel EMG systems) for hardware simplicity, low power consumption, and direct compatibility with analog motor drivers — well suited to embedded, power-constrained prosthetic applications.
