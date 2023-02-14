---
title: >-
  CICC-2022 A 9GHz 72fs-Total-lntegrated-Jitter Fractional-N Digital PLL with
  Calibrated Frequency Quadrupler
toc: true
tags:
  - CICC
  - 2022
  - Polimi
  - PLL
abbrlink: 48280
date: 2023-02-14 23:16:08
---

![Keypoints](https://api2.mubu.com/v3/document_image/976eb283-3fc5-41c6-bb50-65a84801ce90-216525.jpg) \

##### Full Citation

F. Buccoleri et al., "**A 9GHz 72fs-Total-lntegrated-Jitter Fractional-N Digital PLL with Calibrated Frequency Quadrupler**," 2022 IEEE Custom Integrated Circuits Conference (CICC), Newport Beach, CA, USA, 2022, pp. 1-2, doi: 10.1109/CICC53496.2022.9772796.

[IEEE Link](https://ieeexplore.ieee.org/document/9772796) \

## Keypoints

- digital-period-averaging (DPA) algorithm
  - reduce the QN of the ΔΣ DCO
  - Fref x4 by XOR-based doublers
  - DTC delay to reach either T0 or T1 depends on sel[k]
  - T0[k]+T1[k] = Tref/2 always holds and T0[k] and T1[k] converge to Tref/4
- a low-noise true-in-phase combiner (TIPC)
  - combines two PLL cores to reduce phase noise
  - BBPD tracks and cancels the DCOs’ phase offset
  - differentially adding to the FCW of both PLLs

## Background

- multi-core PLL
  - the theoretical PN 3-dB reduction per each doubling of the number of cores
- reduce DSM QN by higher dithering freq
  - an auxiliary PLL which xN Fref
  - a high-speed divider that divides the DCO output
  - the low-frequency error has a white shape which translates into a 1/f2 noise at DCO output
    - pulling effect
    - increasing power and area

![The overall diagram of the proposed digital PLL](https://api2.mubu.com/v3/document_image/f353671f-c43f-4851-96d6-8f32f1a631c5-216525.jpg) \

## Conclusion

**TECH**  28 nm \
**REF**  125 MHz \
**OUT**  8.5~10.5 GHz \
**REF SPUR**  -70.2 dBc \
**FRAC SPUR**  -59.7 dBc \
**POWER**  36 mW \
**RMS JITTER**  71.8 fs \
**FOM**  -248.7 dB \

## Important References

> *require large-range DTC* \
> [4] S. Karman et al., “A 18.9-22.3GHz Dual-Core Digital PLL with On-Chip Power Combination for Phase Noise and Power Scalability,” RFIC Symp., June 2021.
> 
> *quadrupler calibration schemes based on auxiliary PLL [5]* \
> [5] F. Song et al.,“A Fractional-N Synthesizer with 110fsrms Jitter and a Reference Quadrupler for Wideband 802.11ax,” ISSCC, Feb. 2019.
