---
title: >-
  ISSCC-2024 10.1 An 8.75GHz Fractional-N Digital PLL with a Reverse-Concavity
  Variable-Slope DTC Achieving 57.3fsrms Integrated Jitter and −252.4dB FoM
toc: true
tags:
  - ISSCC
  - 2024
  - DPLL
  - BBPD
  - LC
  - DTC
  - Polimi
abbrlink: 1775
date: 2024-10-09 22:54:26
---

![Keypoints](https://s21.ax1x.com/2024/10/09/pAJQG8K.png) \

##### Full Citation

M. Rossoni et al., "**10.1 An 8.75GHz Fractional-N Digital PLL with a Reverse-Concavity Variable-Slope DTC Achieving 57.3fsrms Integrated Jitter and −252.4dB FoM**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 188-190, doi: 10.1109/ISSCC49657.2024.10454388.

[IEEE Link](https://ieeexplore.ieee.org/document/10454388) \

## Keypoints

- reverse-concavity variable-slope DTC
  - C_T --> prop. to DTC_code
    downward concavity
  - R_T --> inversely prop. to DTC_code
    upward concavity
    - compensate the nonlinearity
    - unit R is controlled by a V-DAC to tune the upward concavity
  - noise effect
    - R_T required for is much smaller than output res.
    - R_T and V-DAC has negligible thermal noise and power consumption
- frac-N BB-DPLL
  - coarse RCVS-DTC
    - 128-cell
    - improve linearity with the complementary concavity
  - fine VS-DTC
    - narrow range <--> good linearity
    - good q-noise
  - adaptive concavity zeroing (ACZ)
    - compensated concavity <--> zero quadratic term
    - extract the sign the DTC_INL : a[k] = e[k] * h[k]
    - h[k] = Q[k]^2 ~ |Q[k]| for simplification
    - e[k] = dout_BBPD[k]

## Background

- advanced wireless transceivers
  - high-order modulation schemes
  - high-spectral-purity frequency synthesizers
  - frac-N PLL with digital-to-time converter (DTC)
    - remove time q-error 
    - nonlinearity and noise degrade spectral purity
    - poor fractional spurs and higher in-band noise
- DTCs
  - variable-slope DTC (VS-DTC)
    - the most used
    - linearity is affected by the slope-dependent propagation delay
    - downward concavity
    - adding C_fix trades a better INL for higher noise and power
  - constant-slope DTC (CS-DTC)
    - better linearity
    - similar trade-off of linearity and PN/power
    - worse power-jitter product

<img src="https://s21.ax1x.com/2024/10/09/pAJQlU1.png" width = "500" alt="Block diagram of the implemented PLL and the working principle of the adaptive concavity zeroing algorithm." align=center />

<img src="https://s21.ax1x.com/2024/10/09/pAJQ14x.png" width = "500" alt="Issues of DTC-based fractional-N PLLs and the comparison between conventional and reverse-concavity variable-slope DTCs" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  8.75~10.2 GHz \
**REF SPUR**  -69.4 dBc \
**FRAC SPUR**  -63.4 dBc \
**POWER**  17.5 mW  \
**RMS JITTER**  57.3 fs \
**FOM**  -253.5 dB \

## Important References

> *frac-N PLL with DTC* \
> [1] S. M. Dartizio et al., “A 76.7fs-lntegrated-Jitter and −71.9dBc In-Band Fractional-Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering,” ISSCC, pp. 3-4, Feb. 2023. \
> 
> *VS-DTC* \
> [2] H. Park et al. “A 365fsrms-Jitter and −63dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/Third-Order Nonlinearity Cancelation and a Probability-Density-Shaping ΔΣM,” ISSCC, pp. 442-443, Feb. 2021. \
> [3] A. Santiccioli et al., “Power-Jitter Trade-off Analysis in Digital-to-Time Converters,” Electron. Lett., vol. 53, pp. 306-308, Mar. 2017. \
> [4] W. Wu et al., “A 28-nm 75-fsrms Analog Fractional-N Sampling PLL with a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction,” IEEE JSSC, vol. 54, no. 5, pp. 1254–1265, May 2019. \
> [5] D. Xu et al., “A 6.5-to-8GHz Cascaded Dual-Fractional-N Digital PLL Achieving -63.7dBc Fractional Spurs with 50MHz Reference,” IEEE CICC, pp. 1-2, Apr. 2023. \
> 
> *CS-DTC* \
> [6] J. Ru et al., “A High-Linearity Digital-to-Time Converter Technique: Constant-Slope Charging,” IEEE JSSC, vol. 50, no. 6, pp. 1412-1423, June 2015.
> 
> *frac-N PLL* \
> [7] W. Wu et al., “A 14nm Analog Sampling Fractional-N PLL with a Digital-to-Time Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs at Near- Integer Channels,” ISSCC, pp. 444-445, Feb. 2021. \
> [8] J. Kim et al., “A 104fsrms-Jitter and -61dBc-Fractional Spur 15GHz Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error Cancelation Technique,” ISSCC, pp. 448-449, Feb. 2021.