---
title: >-
  CICC-2024 A 6.0-to-6.9GHz 99fsrms-Jitter Type-II Sampling PLL with Automatic
  Frequency and Phase Calibration Method Achieving 0.62μs Locking Time in 28nm
  CMOS
toc: true
tags:
  - CICC
  - 2024
  - SSPD
  - PLL
  - AFC
  - SUST
  - UMacau
abbrlink: 1046
date: 2024-11-03 21:46:33
---

![Keypoints](https://s21.ax1x.com/2024/11/03/pAr0K0K.png) \

##### Full Citation

J. Yang et al., "**A 6.0-to-6.9GHz 99fsrms-Jitter Type-II Sampling PLL with Automatic Frequency and Phase Calibration Method Achieving 0.62μs Locking Time in 28nm CMOS**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529055.

[IEEE Link](https://ieeexplore.ieee.org/document/10529055) \

## Keypoints

- automatic frequency and phase calibration (AFPC)
  - band selection (BS)
    - operates as a type-I 
    - mapping TDC to the corresponding band
    - avoids the accumulation procedure
  - phase offset cancellation (POC)
    - TDC gives the clear initial state
    - adjust the division ratio of the MMD
  - wide bandwidth locking : large current gm cell
  - narrow bandwidth locking : small current gm cell
- proposed sampling PLL
  - 64-bit TDC
  - Tres changes from 50 to 100ps
  - TDC0 reaches zero and ΔΦ falls within Tres

## Background

- settling time of a frequency synthesizer is crucial
  - power gating
  - dynamic voltage frequency scaling
- ADPLL
  - better convergence speed
  - compatibility with digital algorithm
  - counter-based ADPLL
    - accelerate locking by config. as type-I mode
    - phase offset after type-I loop settles
    - prolongs locking time after switched back to type-II
  - type-II DPLL
    - frequency aid
    - tuning word estimation
    - gear-shift
    - fast-Fourier transform
- type-II sampling PLL
  - high PD gain
  - narrow capture range
  - limited programmable analog LPF
  - out-of-capture range results in a long iteration time

<img src="https://s21.ax1x.com/2024/11/03/pAr0MTO.png" width = "500" alt="block diagram of the proposed type-II sampling PLL with AFPC" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  100 MHz \
**OUT**  6.0~6.9 GHz \
**REF SPUR**  -71.6 dBc \
**POWER**  4.6 mW  \
**RMS JITTER**  99 fs \
**FOM**  -253.5 dB \

## Important References

> *counter-based ADPLL* \
> [1] R. B. Staszewski et al., All-digital frequency synthesizer in deep-submicron CMOS. Hoboken, N.J: Wiley-Interscience, 2006.
> 
> *frequency aid: gearshift* \
> [2] S. M. Dartizio et al., “A fractional-N bang-bang PLL based on type-II gear shifting and adaptive frequency switching achieving 68.6 fs-rms-total-integrated-jitter and 1.56 μs-locking-time,” JSSC, 2022. \
> [3] F. ur Rahman, et al., “A 1–2 GHz computational-locking ADPLL with sub-20-cycle lock time across PVT variation,” JSSC, 2019.
> 
> *tuning word estimation* \
> [4] J. Prinzie et al., “A fast locking 5.8–7.2-GHz fractional-N synthesizer with sub-2-μs settling in 22-nm FDSOI,” SSCL, 2020.
> 
> *fast-Fourier transform techniques* \
> [5] C. -H. Tsai et al., “Analysis of a 28-nm CMOS fast-lock bang-bang digital PLL with 220-fs RMS jitter for millimeter-wave communication,” JSSC, 2020. \
> [6] W. Jung et al., “A 0.99μs FFT-based fast-locking, 0.82GHz-to-4.1GHz DPLL-based input-jitter-filtering clock driver with wide-range mode-switching 8-shaped LC oscillator for DRAM interfaces,” CICC, 2023.
> 
> *type-II sampling PLL* \
> [7] J. Sharma et al., “A 2.4-GHz reference-sampling phase-locked loop that simultaneously achieves low-noise and low-spur performance,” JSSC, 2019.