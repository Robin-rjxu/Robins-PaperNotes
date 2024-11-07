---
title: >-
  CICC-2024 An 11.1-to-14.9GHz Digital-Integral Hybrid-Proportional Fractional-N
  PLL with an LC DTC Achieving 0.52μs Locking Time and 41.3fs Jitter
toc: true
tags:
  - CICC
  - 2024
  - PLL
  - SPD
  - DTC
  - AFC
  - THU
abbrlink: 10662
date: 2024-11-07 20:04:31
---

![Keypoints](https://s21.ax1x.com/2024/11/07/pAywTw6.png) \

##### Full Citation

H. Liu, W. Deng, H. Jia and B. Chi, "**An 11.1-to-14.9GHz Digital-Integral Hybrid-Proportional Fractional-N PLL with an LC DTC Achieving 0.52μs Locking Time and 41.3fs Jitter**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529102.

[IEEE Link](https://ieeexplore.ieee.org/document/10529102) \

## Keypoints

- frac-N fast-hopping hybrid SPLL
  - two modes
    - FLL
      - control voltage is reset to middle point
      - 8b counter counts the integer part (VCO cycles)
      - 6b TDCs measures fractional part
    - PLL
      - SPD / BBPD
      - GM + RC load
      - delta-sigma modulated DAC + LPF
  - finite-state machine (FSM)
    - SAR FLL : 24 ref cycles for 8b OTW
    - incremental FLL : incr/decr by 1
    - phase align : set CKFB_SEL to zero REFD/CKFB offset
    - bandwidth gear shifting (BWGS)
    - closed loop PLL
  - DTC
    - LC coarse DTC
      - 8 inductors
      - 9 output phases
      - 160 ps range
    - RC-based fine DTC
      - reduced range
      - improve noise and linearity
    - LMS gain cali
- two paths
  - same input-referred offsets
    - zero-offset differential SPD
    - zero-offset BBPD
  - analog prop path
    - digital prop and intg path
    - type-II
    - gear shifting
  - after settling
    - type-II
    - digital path has lower gain
    - analog prop + digital intg
- timing
  - quadruple timing margin selection
  - TDC
    - measure time interval
      - D1 = REFD --> CKR (t_RV + 2T_vco)
      - D2 = CKR --> CKRD (3T_vco)
      - t_RV = 3(D1/D2) - 2
    - normalized by measure CKR to CKRD
  - 8b counter
    - f_CKV domain : 2b LSBs
    - f_CKV/4 domain : 6b MSBs
    - 6b MSBs delayed depending on the sampled LSB data
    - always 2Tckv margin for skew of the two clock domain
    - constant offset of input/output of the counter
  - CKFB
    - similar to the divider 
    - retimed by CKV to reduce PN

## Background

- better agility and quality of frequency synthesizer
  - mm-wave bands
  - new generation of wireless communication
  - cognitive radio
- low-jitter PLLs architectures
  - bang-bang digital PLLs (BBPLL)
    - bandwidth gear shifting (BWGS)
    - nolinearity of the BBPD causes sever quantization noise
    - fast-lock PLLs are based on integrator and the incrementally logic
    - long time for wideband hopping
  - analog PLLs
    - linear components
    - well-defined loop parameters
    - inability of fast locking
- adaptive frequency switching
  - estimate the DCO gain
  - predict DCO tuning word
  - rely on the linearity of the code-freq curve

<img src="https://s21.ax1x.com/2024/11/07/pAyw4yR.png" width = "500" alt="Block diagram of the proposed dual-path fast-lock PLL" align=center />

<img src="https://s21.ax1x.com/2024/11/07/pAywoex.png" width = "500" alt="The integrated counter and CKFB generator" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  11.1 ~ 14.9 GHz \
**REF SPUR**  -65.3 dBc \
**FRAC SPUR**  -66.9 dBc \
**POWER**  34 mW  \
**RMS JITTER**  41.3 fs \
**FOM**  -252.4 dB \

## Important References

> *BBPLL* \
> [1] S. M. Dartizio et al., "A 68.6fsrms-total-integrated-jitter and 1.56μs-locking-time fractional-N bang-bang PLL based on type-II gear shifting and adaptive frequency switching," ISSCC, 2022. (adaptive frequency switching) \
> [2] A. Santiccioli et al., "A 66fsrmsJitter 12.8-to-15.2GHz Fractional-N Bang-Bang PLL with Digital Frequency-Error Recovery for Fast Locking," ISSCC, 2020. \
> [3] C. -H. Tsai et al., "Analysis of a 28-nm CMOS Fast-Lock Bang-Bang Digital PLL With 220-fs RMS Jitter for Millimeter-Wave Communication," JSSC, 2020
> 
> *low-jitter analog PLL* \
> [4] X. Geng et al., "A 26GHz Fractional-N Charge-Pump PLL Based on A Dual-DTC-Assisted Time-Amplifying-Phase-Frequency Detector Achieving 37.1fs and 45.6fs rms Jitter for Integer-N and Fractional-N Channels," CICC, 2023. \
> [5] W. Wu et al., "A 14nm Analog Sampling Fractional-N PLL with a Digital-to-Time Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs at Near-Integer Channels," ISSCC, 2021.