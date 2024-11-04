---
title: VLSI-2024 A 5GHz Fractional-N PLL with 97fsrms Jitter and -255.3dB FoM
toc: true
tags:
  - VLSI
  - 2024
  - SSPD
  - DTC
  - PLL
  - HKUST
abbrlink: 38652
date: 2024-11-04 20:41:02
---

![Keypoints](https://s21.ax1x.com/2024/11/04/pAs9tBQ.png) \

##### Full Citation

Z. Huang, F. Chen and S. Kong, "**A 5GHz Fractional-N PLL with 97fsrms Jitter and -255.3dB FoM**," 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631416.

[IEEE Link](https://ieeexplore.ieee.org/document/10631416) \

## Keypoints

- binary-search-based DTC nonlinearity calibration algorithm
  - compensate coarse-fine mismatch
    - measure coarse step with aux-DTC
    - subtract accumulated coarse steps from fine words
    - D_MF=D_DTC - ARY_ACCMF[DMC]
  - step 1 : zero main fine, binary search with aux-DTC
  - step 2 : use aux-DTC words and search (main-DTC - 1) step size
  - flash quantizer generate thermal code for fine main-DTC
- gated-LMS based DTC gain calibration
  - SPD output only generate a narrow pulse
  - enable during the SPD narrow pulse periodically
  - allow DSM-1 and remain DTC tuning range
- frac-N DTC-based PLL
  - main + aux DTC (4b coarse + 10b fine)
  - cancel coarse/fine gain mismatch
  - auxiliary-DTC-based TDC
    - coarse-fine DTC
    - bang-bang PD
  - tree-like DTC
    - n-stage binary-tree topology
    - not increase DTC tuning range
    - minimum delay
    - prevent slow transition
    - keep low jitter
  - DSM-1

## Background

- high-data-rate and millimeter-wave wireless standard
  - low-jitter frac-N PLL
- DTC-based frac-N PLL
  - DTC nonlinearity causes noise folding and frac spur
  - reduce nonlinearity
    - add fixed capacitive loading and bleeding current
    - nonlinearity calibration
  - gain calibration
    - DSM-1 : convergence issues
      - continuous conventional DTC gain calibration
      - require narrow bandwidth
      - slow convergence
      - require HPF before correlation
  - DSM-2 : double DTC tuning range

<img src="https://s21.ax1x.com/2024/11/04/pAs9Yng.png" width = "500" alt="Block diagram of the proposed fractional-N PLL" align=center />

<img src="https://s21.ax1x.com/2024/11/04/pAs9N7j.png" width = "500" alt="DTC nonlinearity correction" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  100 MHz \
**OUT**  4.9~7.3 GHz \
**REF SPUR**  -77 dBc \
**FRAC SPUR**  -62 dBc \
**POWER**  3.15 mW  \
**RMS JITTER**  97 fs \
**FOM**  -255.3 dB \

## Important References

> *fractional-N phase-locked-loop (PLL) with low integrated jitter* \
> [1] W. Wu, IEEE JSSC, 5, 1254. 2019. (improve DTC linearity by adding fixed capacitive loading) \
> [2] W. Wu, ISSCC, 2021, pp.444 (DTC-based sampling PLL architecture)
> 
> *Nonlinearity calibration* \
> [3] N. Markulic, IEEE JSSC, 12, 3078. 2016. \
> [4] C. Hwang, IEEE JSSC, 09, 2841. 2022. 
> 
> *2nd-order DSM* \
> [5] L. Bertulessi, IEEE JSSC, 12, 3493. 2019.
> 
> *Conventional DTCs using switched-capacitor* : [1-4] \
> 
> *N-to-1 multiplexer (MUX)* \
> [6] F. Buccoleri, IEEE JSSC,, 3, 634, 2023.
> 
> [7] M. Mercandelli, ISSCC, 2020, pp. 274  \
> [8] S. M. Dartizio, ISSCC, 2022, pp. 386 \
> [9]G. Castoro, ISSCC, 2023, pp. 82 \