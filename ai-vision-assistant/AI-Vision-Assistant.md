# AI Vision for Blind: IoT-Based Real-Time Scene Description System

**Status:** Submitted to IEEE Access, 2025 (under review)
**Co-authors:** Sajal Patil, Aditi Pore, Dr. Nilima R. Kolhare — Dept. of Electronics and Telecommunication Engineering, COEP Technological University (Microcontrollers and its Applications Lab)

## Overview

An embedded, AI-powered assistive device for visually impaired users that captures a scene, generates a natural-language description using a large vision-language model, and speaks it aloud — all from a single button press, with no smartphone, laptop, or GPU required.

## System Architecture

Built entirely around an **AI-Thinker ESP32-CAM** module:

```
Push Button → ESP32-CAM (Capture) → Wi-Fi → Groq API (LLaMA-4 Scout)
                                                    ↓
Speaker ← MAX98357A (I2S Amp) ← Google TTS ← Text Response
                    ↓
              SSD1306 OLED (scrolling display)
```

**Hardware:** ESP32-CAM (2MP OV2640 camera, 240 MHz dual-core), MAX98357A I2S Class-D audio amplifier, SSD1306 OLED display, single push-button interface — total BOM cost under ₹1,500.

## Pipeline

1. User presses button → ESP32-CAM captures a JPEG image (with flash + warm-up frames discarded for exposure stability)
2. Image is Base64-encoded on-device and sent via HTTPS to the Groq API
3. Groq's LLaMA-4 Scout (17B) vision-language model generates a natural-language scene description
4. Response is parsed, chunked (≤200 characters per chunk to respect Google TTS URL limits), and streamed to speech via I2S
5. Description simultaneously scrolls on the OLED display for sighted companions/caregivers
6. A long-press cancel mechanism allows interrupting playback at any stage

## Engineering Challenges Solved

- **Wi-Fi resilience:** custom reconnect logic with disabled modem sleep to prevent the intermittent TCP drops common in ESP32 power-saving mode
- **Memory management:** explicit heap clearing of large Base64/JSON buffers after each request cycle to preserve headroom for SSL/TLS sessions on a memory-constrained microcontroller
- **Pin conflicts:** re-mapped I2C pins (since the camera module occupies the default I2C bus) and assigned I2S to a separate hardware port from the camera's clock generator

## Results

- **88% description accuracy** across 50 capture cycles spanning indoor, outdoor, and text-bearing scenes
- **Average end-to-end latency: 4.3 ± 0.9 seconds** from button press to first audio output
- Zero Wi-Fi dropouts across all test sessions
- Power draw: ~320 mA active, ~95 mA idle — supporting 6–8 hours of continuous use on a 10,000 mAh power bank

## Why It's Relevant to My Background

This project is my clearest embedded-systems-plus-AI integration work — combining low-level firmware (Wi-Fi management, I2S audio streaming, memory-constrained buffer handling) with a modern cloud AI pipeline, all running on a sub-₹1,500 hardware budget.
