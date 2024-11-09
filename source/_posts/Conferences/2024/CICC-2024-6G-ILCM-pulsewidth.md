---
title: >-
  CICC-2024 An Injection-Locked Clock Multiplier with Adaptive Pulsewidth
  Adjustment and Phase Error Cancellation Achieving 43.9fs RMS Jitter and
  -255.5dB FoM
toc: true
tags:
  - CICC
  - 2024
  - ILCM
  - CAS
abbrlink: 5566
date: 2024-11-09 17:03:10
---

![Keypoints](https://s21.ax1x.com/2024/11/09/pA63wwQ.png) \

##### Full Citation

Y. He et al., "**An Injection-Locked Clock Multiplier with Adaptive Pulsewidth Adjustment and Phase Error Cancellation Achieving 43.9fs RMS Jitter and -255.5dB FoM**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529037.

[IEEE Link](https://ieeexplore.ieee.org/document/10529037) \

## Keypoints

- optimal injection pulse width
  - adaptive pulse width adjustment
  - complementary-injection scheme
    - narrow pulse
    - short the P/N outputs
    - main phase tracking
    - ahead or lag the crossing point
  - wide pulses
    - phase error cancellation
    - drive the cross-connected inverters
    - inverted polarity 
- proposed ILCM
  - adaptive pulse generator (APG)
  - four-stage RVCO
    - single-ended narrow pulse
      - optimal and constant width of T0/4
      - also to the noise suppression bandwidth
      - analysis with ISF theory
    - differential wide pulses
      - slightly wider than T0/2
- FTL

## Background

- multi-phase clock generators
  - modern wireline transceiver
  - optimize jitter performance
- injection-locked clock multipliers (ILCMs) based on RVCOs
  - low jitter
  - energy efficient
  - small footprint
  - multiple phases
- phase accuracy and jitter performance limitation
  - non-optimal pulse width
    - drift with PVT variations
    - degrade the PN suppression
    - deteriorate the robustness and reliability
  - static phase error
    - accelerate/slow edge transition
    - crossing point deviation

<img src="https://s21.ax1x.com/2024/11/09/pA63deg.png" width = "500" alt="Overall architecture of the proposed ILCM and the optimal pulsewidth principle" align=center />

<img src="https://s21.ax1x.com/2024/11/09/pA630oj.png" width = "500" alt="Schematic and the working principle of the proposed complementary-injection RVCO " align=center />

## Conclusion

**TECH**  28 nm \
**REF**  3 GHz \
**OUT**  3.9 ~ 7.8 GHz \
**REF SPUR**  -59 dBc \
**POWER**  14.5 mW  \
**RMS JITTER**  43.9 fs \
**FOM**  -255.5 dB \

## Important References

> *ILCMs* \
> [1] Z. Wang et al., "Multi-Phase Clock Generation for Phase Interpolation With a Multi-Phase, Injection-Locked Ring Oscillator and a Quadrature DLL," JSSC, June. 2022. \
> [2] S. Park et al., “A 97fsrms-Jitter and 68-Multiplication Factor, 8.16GHz Ring-Oscillator Injection-Locked Clock Multiplier with Power-Gating Injection-Locking and Background Multi-Functional Digital Calibrator,” ISSCC, Feb. 2022.
> 
> *injection strength* \
> [3] X. Zheng et al., “Frequency-Domain Modeling and Analysis of Injection-Locked Oscillators,” JSSC, June. 2020.
> 
> *optimal jitter when close to free-freq : [1-6] *\
> [4] S. Kundu et al., “A Self-Calibrated 1.2-to-3.8GHz 0.0052mm2 Synthesized Fractional-N MDLL Using a 2b Time-Period Comparator in 22nm FinFET CMOS,” ISSCC, Feb. 2020. *\
> [5] K. M. Megawer et al., “A 5GHz 370fsrms 6.5mW clock multiplier using a crystal-oscillator frequency quadrupler in 65nm CMOS,” ISSCC, Feb. 2018. \
> [6] S. Yang et al., "A 0.0056-mm2 −249-dB-FoM All-Digital MDLL Using a Block-Sharing Offset-Free Frequency-Tracking Loop and Dual Multiplexed-Ring VCOs," JSSC, Jan. 2019.