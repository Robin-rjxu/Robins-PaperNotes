---
title: VLSI-2024 A 94fsrms-Jitter and −249.3dB FoM 4.0GHz Ring-Oscillator-Based MDLL with Background Calibration of Phase Offset and Injection Slope Mismatch
toc: true
tags:
  - VLSI
  - 2024
  - MDLL
  - ILCM
  - RO
  - POSTECH
abbrlink: 39944
date: 2024-10-28 20:17:32
---

![Keypoints](https://s21.ax1x.com/2024/10/28/pA0WqbR.png) \

##### Full Citation

D. Park, H. Roh, S. -K. Lee and J. -Y. Sim, "**A 94fsrms-Jitter and −249.3dB FoM 4.0GHz Ring-Oscillator-Based MDLL with Background Calibration of Phase Offset and Injection Slope Mismatch,**" 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631486.

[IEEE](https://ieeexplore.ieee.org/document/10631486) \

## Keypoints

- RO-based MDLL
  - frequency and slope detector (FSD)
    - oscillation frequency
    - injection slope
    - two types of buffers BUF_H/L 
      - stacked diode-connected N/P device in pull-up/dn paths
      - shift inverter threshold
      - cause larger difference in upper/lower parts for slope mismatch
    - measure pulse width
    - phase offset does not affect BUF_H/L output
- circuits
  - BUF_H/L extract slope error as voltages
  - store voltage in capacitors by CPs
  - sample two consecutive two pulses 
  - comparator results can use as to distinguish error causes
  - transition slope controller (TSC)
    - digitally-controlled shunt cap
    - for ref edge and RO
- operation
  - compare two consecutive transitions
  - distinguish mismatch in period or slope
- two loops and cali
  - frequency locking
  - match transition RO output slope
  - internal path calibration loop for path mismatch
    - two non-injected identical pulses
    - adjust capacitance

## Background

- ILCM has outstanding jitter
  - injection clean oscillator edges
  - MDLL is the ILCM that features injection strength of 1
- ref edge effects
  - force a phase
  - closed-loop control with a PD
    - phase mismatch
    - distort output shape
- background calibration
  - calibration with time-to-voltage converter
  - DCDL-based period sampling
  - DTC-based time-period comparison
  - injection gating
  - consider transition time
  - cannot distinguish the transition slope and phase offset

<img src="https://s21.ax1x.com/2024/10/28/pA0Wbr9.png" width = "500" alt="Overall block diagram of the MDLL with the proposed FSD" align=center />

<img src="https://s21.ax1x.com/2024/10/28/pA0WOV1.png" width = "500" alt="Schematic and timing diagrams of the proposed FSD" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  250 MHz \
**OUT**  4.0 GHz \
**REF SPUR**  -54 dBc \
**POWER**  13.3 mW  \
**RMS JITTER**  94 fs \
**FOM**  -249.3 dB \

## Important References

> *calibration with time-to-voltage converter* \
> [1] H. Kim, JSSC, 2017, pp. 2934. 
> 
> *DCDL-based period sampling* \
> [2] S. Yang, JSSC, 2019, pp. 88.
> 
> *DTC-based time-period comparison* \
> [3] S. Kundu, JSSC, 2021, pp. 43.
> 
> *injection gating* \
> [4] Q. Zhang, JSSC, 2022, pp. 80.
> 
> *consider transition time* \
> [5] S. Yoo, JSSC, 2021, pp. 298.