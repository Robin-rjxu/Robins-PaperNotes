---
title: >-
  VLSI-2024 A 25.4-27.5 GHz Ping-Pong Charge-Sharing Locking PLL Achieving 42 fs
  Jitter with Implicit Reference Frequency Doubling
toc: true
tags:
  - VLSI
  - 2024
  - PLL
  - CSL
  - USD
abbrlink: 51502
date: 2024-10-24 20:54:16
---

![Keypoints](https://s21.ax1x.com/2024/10/24/pAwnqQx.png) \

##### Full Citation

S. Kumar, P. Sawakewang, T. Siriburanon and R. B. Staszewski, "**A 25.4-27.5 GHz Ping-Pong Charge-Sharing Locking PLL Achieving 42 fs Jitter with Implicit Reference Frequency Doubling**," 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631558.

[IEEE Link](https://ieeexplore.ieee.org/document/10631558) \

## Keypoints

- ping-pong charge-sharing locking (CSL)
  - two ref phases of 50% duty cycle are used in ping-pong manner
  - not rely on the narrow pulse width
  - higher injection efficiency
  - wider possible bandwidth
- duty-cycle calibration
  - charge residues can be read out and reused for DCC
  - implict 2x reference multiplication
  - DAC CM-voltage acquisition
    - connect during the complementary phases
    - disconnect ping-pong hands
- implementation
  - either C_share or C_share' attaches to the LC tank
  - FTL and DCC has the similar circuits
    - sample the charge residue
    - auxiliary BBPD 
  - class-F23 oscillator
    - complementary charge-sharing capacitors
    - 3rd harmonic extractor (H3E)
    - switches cancel feedthrough
  - Ferr and  DC_err calibration
    - BBPDs
    - integrated and multiplied by the attenuation factor
    - errors can occur simultaneously
    - one type will be corrected at a time
    - range cover half of the OSC period

## Background

- complex modulation schemes -->ultra-low jitter PLL
- analog PLL
  - charge-pump, sampling/sub-sampling PD
  - analog loop flter
  - large area
  - high power
- injection-lock (IL) PLL
  - require FTL
  - accurate timing control
- charge-sharing locking
  - digitally control of the charge injected to the LC tank
  - manual tuned injection pulse width
  - narrow pulse width, weak injection strength
  - lower bandwidth
  - precise CM-voltage control



## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  25.4~27.5 GHz \
**REF SPUR**  -60.5 dBc \
**POWER**  14 mW  \
**RMS JITTER**  41.75 fs \
**FOM**  -256.3 dB \

## Important References

> *analog PLL* \
> [1] D. Turker, a at, ISSCC, pp. 378-380, 2018.  \
> [2] Y. Zhao, et at, VLSI Circuits, pp. 1-2, 2021.  \
> [3] X. Geng, et at, ISSCC, pp. 388-390, 2022.  \
> [4] J. Gong, et at, JSSC, pp. 492-504, 2022.  \
> 
> *charge-sharing locking* \
> [7] Y. Hu, a at, JSSC, pp. 518-534, 2022. 
> 
> *class-F23 oscillator with 3rd-harmonic extractor* \
> [8] Y. Hu, a at, JSSC, pp. 1977-1987, 2018. 
> 
> [5] E. Thaller, et at, ISSCC, pp. 451-453, 2021.  \
> [6] W. Tao, et at, VLSI Circuits, pp. 1-2, 2023.  \