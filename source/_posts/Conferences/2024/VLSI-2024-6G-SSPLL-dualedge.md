---
title: >-
  VLSI-2024 A 6.5-to-6.9-GHz SSPLL with Configurable Differential Dual-Edge SSPD
  Achieving 44-fs RMS Jitter, -260.7-dB FOMJitter, and -76.5-dBc Reference Spur
toc: true
tags:
  - VLSI
  - 2024
  - SSPD
  - PLL
  - CAS
abbrlink: 50280
date: 2024-11-03 22:29:07
---

![Keypoints](https://s21.ax1x.com/2024/11/03/pArBwK1.png) \

##### Full Citation

T. Chen et al., "**A 6.5-to-6.9-GHz SSPLL with Configurable Differential Dual-Edge SSPD Achieving 44-fs RMS Jitter, -260.7-dB FOMJitter, and -76.5-dBc Reference Spur**," 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631396.

[IEEE Link](https://ieeexplore.ieee.org/document/10631396) \

## Keypoints

- dual-edge SSPLL
  - switch even mode ando dd mode
  - without freq resolution degradation
  - reducing XO and RBUF requirement
  - save power and better FoM
- implementation
  - dual-edge SSPD
    - square-wave reference
    - differentially
    - each VCO output pair will be sampled twice
  - GM
    - 3 identical GM cells
    - only 2 of them are enabled
  - RBUF : DCC by tuning CM input voltage
  - FLL : PLL (PFD, CP, DZ, MMD)
  - LC-VCO and LF

## Background

- low-jitter clock
  - communication systems
  - higher data rate
- sampling-type PLLs
  - greatly suppress noise and jitter
  - reference sampling PLL (RSPLL)
    - balance spur and jitter well
    - low PD gain
    - type-I topology
  - sub-sampling (SSPLL)
    - need retimer after divider
    - ref buffer limits the in-band PN
      - noise sensitive
      - high-power
      - large area
    - need high-cost ultra low-noise XO
- dual-edge sampling PLL (SPLL)
  - sample only two fixed rising/falling edges within a ref period
  - DIV2 after MMD 
  - degrade frequency resolution
  - large size to drive the MMD

<img src="https://s21.ax1x.com/2024/11/03/pArBavR.png" width = "500" alt="Overall Architecture of Proposed SSPLL with Differential Dual-Edge SSPD" align=center />

<img src="https://s21.ax1x.com/2024/11/03/pArBBb6.png" width = "500" alt="Comparison of different type-II S/SSPLL architectures" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  100 MHz \
**OUT**  6.5~6.9 GHz \
**REF SPUR**  -76.5 dBc \
**POWER**  4.4 mW  \
**RMS JITTER**  44 fs \
**FOM**  -260.7 dB \

## Important References

> *Low-jitter clock generators* \
> [1] B. Razavi, TCAS-I, 2021.
> 
> *sampling-type PLL shows better jitter* \
> [2] Z. Yang, VLSI, 2023. (type-I topology ) \
> [3] J. Gong, JSSC, 2022.
> 
> *retimer after the divider chain* \
> [4] Y. Li, A-SSCC, 2023. \
> [5] Y. Zhao, VLSI, 2021. (dual-edge with DIV2)