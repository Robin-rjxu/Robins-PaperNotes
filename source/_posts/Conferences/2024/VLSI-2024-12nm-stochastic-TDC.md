---
title: >-
  VLSI-2024 Synthesizable 10-bit Stochastic TDC Using Common-Mode Time Dithering
  and Passive Approximate Adder with 0.012mm2 Active Area in 12nm FinFET
toc: true
tags:
  - VLSI
  - 2024
  - TDC
  - dither
  - USC
  - UVirginia
abbrlink: 57135
date: 2024-10-23 21:00:32
---

![Keypoints](https://s21.ax1x.com/2024/10/23/pAd5kqA.png) \

##### Full Citation

Q. Zhang, S. Su, B. R. Biswas, S. Gupta and M. S. -W. Chen, "**Synthesizable 10-bit Stochastic TDC Using Common-Mode Time Dithering and Passive Approximate Adder with 0.012mm2 Active Area in 12nm FinFET**," 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631528.

[IEEE Link](https://ieeexplore.ieee.org/document/10631528) \

## Keypoints

- proposed stochastic TDC (STDC)
  - common-mode time dithering
    - phase folder outputs a time-error pulse
    - only one PN modulated DTC
    - shift pulse
    - exercise different section of the TDC and scramble the INL
    - no need to remove dithering noise
  - passive approximate adders
    - OA = 2 Ci + A
    - only two physical connection
    - error is only introduced when not all ones/zeros
    - negligible INL degradation

## Background

- high-res, low-cost TDC
  - for mixed-signal system
  - such as time-based ADC, digital PLLs, LiDAR
  - precise time references
  - stringent matching
  - on-chip calibration
- stochastic TDCs
  - use device mismatch and jitter to mitigate nonlinearity
  - require excessive number  of time references/comparators/encoder
  - large area and power consumption
- conventional implementation
  - time dithering
    - PN modulated DTC
    - differentially between two TDC inputs
    - adaptive filter to remove dither noise
    - extra overhead
    - long convergence time
  - unary to binary encoder
    - full/half adder
    - large area and power


<img src="https://s21.ax1x.com/2024/10/23/pAd5Frd.png" width = "500" alt="Blocks of the proposed STDC" align=center />

<img src="https://s21.ax1x.com/2024/10/23/pAd5EVI.png" width = "500" alt="STDC overview and design challenges" align=center />

## Conclusion

**TECH**  12 nm FinFET \
**FREQ**  100 MHz \
**RANGE**  ±3.9 ns \
**ENOB**  9.3 bits \
**INL**  0.61 LSB \
**POWER**  2.68 mW  \
**AREA**  19.1 um2/conv.-step \
**FOM**  160 dB \

## Important References

> *TDC in time-based ADC* \
> [1] S.-J. Kim, VLSI, 2020, doi:10.1109NLSICircuits18222.2020.9162800. 
> [2] S. Su, CICC, 2023, doi: 10.1109/CICC57935.2023.10121292. 
> 
> *TDC in PLLs* \
> [3] Q. Zhang, JSSC, 2021, doi: 10.1109/JSSC.2021.3098009.
> 
> *stochastic TDC* \
> [4] S.-J. Kim, ISSCC, 2015, doi: 10.1109/ISSCC.2015.7063035. \
> [5] H. Chung, JSSC, 2021, doi: 10.1109/JSSC.2020.3036960. 
> 
> *conventional differential DTC PN modulation* \
> [6] Q. Zhang, DAC, 2022, doi: 10.1145/3489517.3530502. 