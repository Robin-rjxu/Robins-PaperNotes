---
title: >-
  CICC-2024 An 8-14GHz 180fs-rms DTC-Less Fractional ADPLL with ADC-Based Direct
  Phase Digitization in 40nm CMOS
toc: true
tags:
  - CICC
  - 2024
  - PLL
  - ADC
  - VCO
  - FDU
abbrlink: 22420
date: 2024-11-05 19:16:13
---

![Keypoints](https://s21.ax1x.com/2024/11/05/pAs03GQ.png) \

Full Citation
Y. Wang et al., "**An 8-14GHz 180fs-rms DTC-Less Fractional ADPLL with ADC-Based Direct Phase Digitization in 40nm CMOS**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529006.

[IEEE Link](https://ieeexplore.ieee.org/document/10529006) \

## Keypoints

- wideband fractional-N PLL
  - direct phase error digitization
  - integrator-based time-to-voltage converter
    - gain boosting amplifiers
    - high detection gain suppresses the noise
    - intrinsic high linearity
    - 2V/ns --> 0.54 ps/b
- 10b SAR ADC
  - differential ramping voltage
  - linearity
    - choosing the crossing point as the locking reference
    - voltage offset to VDD/2 (Vth = 300/800 mV)
    - only limited by the cap matching
    - offset and differential mismatch do not impact
- operation
  - two current source charge/discharge the SAR cap array
  - ref clock samples the ramping voltage
  - quantize by the 10b charge redistribution SAR ADC
- circuits
  - current source
    - cascode transistor
    - gain boosting amplifiers
  - 10b SAR ADC
    - 11b asynchronous
    - 1b redundancy
    - 0.4 mV resolution
  - double-tail dynamic comparator
    - shield the core latch from large-range input
    - constant input-referred offset
  - 2nd-order DSM : ±2Tvco
  - dual-mode VCO
    - 8-14G wide range
    - controlling both magnetic and electric coupling strength
    - figure-8 shape inductor
    - cross-coupled pair eliminates the mode ambiguity

## Background

- PLLs for high-speed communication systems
  - wide frequency coverage
  - fine freq resolution
  - low phase noise
- fractional PLLs
  - DTC-based quantization
  - voltage domain quantization
    - employing ADCs
    - linear quantization
    - nonlinear time-to-voltage conversion
    - frac spur and noise folding
- linearity compensation
  - digital processing
  - DTC or DAC
    - generate QN replica of the frac-div
    - cancel out it in the analog domain

<img src="https://s21.ax1x.com/2024/11/05/pAs01Pg.png" width = "500" alt="Overall architecture of the proposed PLL of the ADC-based direct phase digitization." align=center />

<img src="https://s21.ax1x.com/2024/11/05/pAs0QIS.png" width = "500" alt="Circuit implemention of the proposed phase detector" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  100 MHz \
**OUT**  8 ~ 14 GHz \
**REF SPUR**  -57.2 dBc \
**FRAC SPUR**  -57 dBc \
**POWER**  17~21 mW  \
**RMS JITTER**  180 fs \
**FOM**  -242 dB \

## Important References

> *ADC PLL with digital linearization* \
> [1] Z. Chen et al., “A Sub-Sampling All-Digital Fractional-N Frequency Synthesizer with -111dBc/Hz In-Band Phase Noise and an FOM of -242dB”, ISSCC, 2015. \
> [2] Z. Xu et al, “A 3.6 GHz Low-Noise Fractional-N Digital PLL Using SAR-ADC-Based TDC”, JSSC, 2016.
> 
> *DTC/DAC cancel QN* \
> [3] X. Gao et al., “A 2.7-to-4.3GHz, 0.16psrms-Jitter, -246.8dB-FOM, Digital Fractional-N Sampling PLL in 28nm CMOS”, ISSCC, 2016. \
> [4] Y. Chen et al., “Fractional-N Digitally Intensive PLL Achieving 428-fs Jitter and <−54-dBc Spurs Under 50-mVpp Supply Ripple”, JSSC, 2022.
> 
> *DTC-based PLLs* \
> [5] C. Hwang et al., “A 188fsrms-Jitter and –243dB-FoMjitter 5.2GHz-Ring-DCO- Based Fractional-N Digital PLL with a 1/8 DTC-Range-Reduction Technique Using a Quadruple-Timing-Margin Phase Selector”, ISSCC, 2022. \
> [6] S. M. Dartizio et al., “A 76.7fs-Integrated-Jitter and -71.9dBc In-Band Fractional- Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering”, ISSCC, 2023.