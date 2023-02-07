---
title: ISSCC-2022 A 97fsrms-Jitter and 68-Multiplication Factor, 8.16GHz Ring-Oscillator Injection-Locked Clock Multiplier with Power-Gating Injection-Locking and Background Multi-Functional Digital Calibrator
toc: true
date: 2023-02-07 22:51:55
tags:
  - ISSCC
  - 2022
  - ILCM
  - KAIST
---

![Keypoints](https://api2.mubu.com/v3/document_image/18318f18-d225-437a-b6c1-003232b47934-216525.jpg) \

##### Full Citation

S. Park, S. Yoo, Y. Shin, J. Lee and J. Choi, "**A 97fsrms-Jitter and 68-Multiplication Factor, 8.16GHz Ring-Oscillator Injection-Locked Clock Multiplier with Power-Gating Injection-Locking and Background Multi-Functional Digital Calibrator**," 2022 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 1-3, doi: 10.1109/ISSCC42614.2022.9731713.

[IEEE Link](https://ieeexplore.ieee.org/document/9731713) \

## Keypoints

- two complementary power-gating DCOs
- combining their outputs seamlessly
- calibration for evenly spaced all output edges
    - DCO periods
    - power gating pulse width
    - delay line as the reference indicator
- circuits
    - phase-rotational div-4 reserves the freq resolution
    - multiple calibrations with different bandwidth
    - bidirectional pulse width adjustment
        avoids 50% duty cycle requirement

## Background

- ILCMs have two main issues
    - jitter performance is sensitive to PVT
    - stability and jitter degrade as large multiplying factor
- power-gating provides strong effective injection
    - the output is only partially available

<img src="https://api2.mubu.com/v3/document_image/cd7a6393-235e-4050-ad44-7c35f6a80ec8-216525.jpg" width = "500" alt="Overall architecture of the proposed PG-ILCM" align=center />

## Conclusion

**TECH** 65 nm
**REF** 120 MHz
**OUT** 7.68~8.52 GHz
**REF SPUR** -55 dBc
**FRAC SPUR** NA
**POWER** 14.3 mW
**RMS JITTER** 97 fs
**FOM** -248.7 dB

## Important Reference

> *proposed power-gating injection-locked clock multiplier*
> [6] C. Jany et al., “A Programmable Frequency Multiplier-by-29 Architecture for Millimeter Wave Applications,” IEEE JSSC, pp. 1669-1679, July 2015.
>
> *previous work at 102G*
> S. Yoo et al., "23.4 An 82fsrms-Jitter and 22.5mW-Power, 102GHz W-Band PLL Using a Power-Gating Injection-Locked Frequency-Multiplier-Based Phase Detector in 65nm CMOS," IEEE ISSCC, 2021.

