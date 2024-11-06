---
title: >-
  VLSI-2024 A 9-GHz Subsampling-Chopper PLL with Charge-Share Cancelling and
  Achieving 57.8-fs-rms Jitter with 15dB In-Band Noise Improvement
toc: true
tags:
  - VLSI
  - 2024
  - PLL
  - SSPD
  - CP
  - chopping
  - GUT
abbrlink: 28434
date: 2024-11-06 17:10:21
---

![Keypoints](https://s21.ax1x.com/2024/11/06/pAsxVAI.png) \

##### Full Citation

X. Kong, K. Xu, R. B. Staszewski, M. Jian and C. Guo, "**A 9-GHz Subsampling-Chopper PLL with Charge-Share Cancelling and Achieving 57.8-fs-rms Jitter with 15dB In-Band Noise Improvement**," 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631552.

[IEEE Link](https://ieeexplore.ieee.org/document/10631552) \

## Keypoints

- chopping CP
  - need rail-to-rail CM-FB to remove CM noise
- charge-sharing cancellation (CSC)
  - the nonlinearity is mostly from parasitic Cpar and LP C1
  - swapping the same polarity ΔQ' = C_par (V_n(k-2)
  - preserved voltage in C_par minimize the charge exchange
- circuits
  - high chopping rate (Fref/2)
  - four-way CP
    - separate the pushing/pulling paths into PUL_S1 and PUL_S2 
    - duplicated paths
      - differential operation
      - facilitate the OTA-based voltage preservation
      - clocked by PUL_csc1 and PUL_csc2
  - four OTAs configured as unity-gain buffer 
    - 1/f noise from OTA is also modulated
  - NMOS-only class-C/F2 VCO
    - F-1 for both CM and DM
    - class-C operation to reduce 1/f3 corner

## Background

- SS-PLL 
  - low in-band phase noise
  - large gain of the SS-PD
  - enlarge PD gain by increasing biasing current
- CP 1/f noise is still a major contributor
  - increase MOS length
  - limited with technology scaling
  - mere chopping
    - swapping ΔV = V_p - V_n
    - nonlinearity 
      - mainly caused by charge sharing of switches
      - residual offset
      - periodic spike
      - impact settling time
- enlarge VCO buffer
  - burn more power
  - large kick-back 
- type-I SS-PLL
  - no CP
  - lack of integration
  - narrow locking range
  - large variation of PD gain
- complementary class-F-1
  - boast excellent PN
  - degrade 1/f3 corner
  - naturally unbalanced NMOS/PMOS

<img src="https://s21.ax1x.com/2024/11/06/pAsxkBd.png" width = "500" alt="charge-sharing induced impairments and the chopping and CSC" align=center />

<img src="https://s21.ax1x.com/2024/11/06/pAsxAHA.png" width = "500" alt="implementation details of the chopping CP with CSC" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  100 MHz \
**OUT**  8.54 ~ 9.4 GHz \
**REF SPUR**  -58 dBc \
**POWER**  7.5 mW  \
**RMS JITTER**  57.8 fs \
**FOM**  -256 dB \

## Important References

> *increase the MOS length to reduce 1/f noise* \
> [1] C-T. Ko, JSSC, pp. 1043, 2020.
> 
> *PLL at sub-1V* \
> [2] Z. Zhang, JSSC, pp. 1665, 2020. \
> [3] Y. Wang, JSSC, pp. 2252, 2023.
> 
> *type-I SSPLL* \
> [4] A. Sharkia, ISSCC, pp. 520, 2018. \
> [5] Y. Zhao, VLSI, pp. 1-2, 2021.
> 
> *chopping CP* \
> T. N. Lin, TCAS-II, pp. 299, 2021.
> 
> *complementary class-F1 VCO* \
> [7] C. C. Lim, JSSC, pp. 3528, 2018.