---
title: >-
  ISSCC-2024 10G-FMCW-BB-DPLL-nonuniform-PWL-DPD 10.6 A 10GHz FMCW Modulator
  Achieving 680MHz/μs Chirp Slope and 150kHz rms Frequency Error Based on a
  Digital-PLL with a Non-Uniform Piecewise-Parabolic Digital Predistortion
toc: true
tags:
  - ISSCC
  - 2024
  - DPLL
  - BBPD
  - FMCW
  - DCO
  - DPD
  - Polimi
abbrlink: 22785
date: 2024-10-15 21:02:40
---

![Keypoints](https://s21.ax1x.com/2024/10/15/pAtx8fI.png) \

##### Full Citation

F. Tesolin et al., "**10.6 A 10GHz FMCW Modulator Achieving 680MHz/μs Chirp Slope and 150kHz rms Frequency Error Based on a Digital-PLL with a Non-Uniform Piecewise-Parabolic Digital Predistortion**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 198-200, doi: 10.1109/ISSCC49657.2024.10454289.

[IEEE Link](https://ieeexplore.ieee.org/document/10454289) \

## Keypoints

- low-noise wide-range DCO
  - low inductance value L_tank
  - large area capacitor bank
  - minimizing the FM error
  - non-smooth DCO tuning charateristic
    - C-to-Freq 1/√ dependency
    - discontinuous derivatives at the row-switching codes
- PWL-DPD
  - map the digital modulation signals
  - increasing the number of points in the grid
  - additional hardware resources
- non-uniform PWL-DPD
  - use a grid of non-uniformly spaced points X_j
  - X_row_i are adaptively calibrated belong to the grid
  - second-order polynomial interpolation instead of the linear one
  - implementation
    - 9 non-uniformly spaced Xj grid points
      - X2, X4, X6 grid points are set by the adaptive point-calibration units (APCU)
      - X1, X3, X5, and X7 grid points are the average between their adjacent points
    - 9 corresponding Hj values of the inverse function
      - H2, H4, and H6 values are fixed to 16, 32, and 48 \
        the inverse function at Xrow1, Xrow2, and Xrow3
      - the adaptive height-calibration units (AHCU) provide the remaining Hj values
    - converge to nullify the first-order difference of the PLL-phase-detector output e[k]
    - the non-smooth Hinv(.) function can be split in four sections 
      - approximated with a parabola
      - coefficients are estimated by a second-order polynomial engine with 3 grid points
- proposed FMCW BB DPLL
  - segmented capacitor bank coarse/mid/fine
  - DSM and QE to fine stages
  - other calibrations
  - DCO mid/fine bank gain calibration
    - digital timing skew calibration
    - DTC gain calibration

## Background

- CMOS FMCW radars
  - spatial resolution
  - reliability
- FMCW digital PLL using the two-point modulation (TPM)
  - fast and wide-bandwidth chirp modulation
  - short retrace time
  - low power area and phase noise
- the non-linearity of the DCO degrades chirp linearity
  - significant spurs and false target
  - trade-off between linearity and phase noise
- improve DCO linearity
  - induced by the practical layout
  - piecewise-linear digital predistortion (PWL-DPD)
    - mitigates DCO linearity
    - limited effectiveness in non-smooth DCO tuning curves
  - non-uniform piecewise-parabolic digital predistortion
    - specially mitigate non-smooth DCO non-linearies


<img src="https://s21.ax1x.com/2024/10/15/pAtx3tA.png" width = "500" alt="Block diagram of the implemented digital PLL" align=center />

<img src="https://s21.ax1x.com/2024/10/15/pAtx1kd.png" width = "500" alt="DCO non-linearity issue in FMCW modulators and DPD techniques" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  9.25~10.5 GHz \
**MAX BW CHIRP**  680 MHz \
**MAX SLOPE**  647 MHz/us \
**MAX FM ERROR RMS** 151 KHz \
**REF SPUR**  -70 dBc \
**FRAC SPUR**  -53.7 dBc \
**POWER**  21 mW  \
**RMS JITTER**  87.1 fs \
**FOM**  -248 dB \

## Important References

> *FMCW digital PLL using two-point modulation* \
> [1] D. Cherniak et al., “A 23GHz Low-Phase-Noise Digital Bang-Bang PLL for Fast Triangular and Saw-Tooth Chirp Modulation,” ISSCC, pp. 248-249, Feb. 2018 \
> [2] H. Shanan et al., “A 9-to-12GHz Coupled-RTWO FMCW ADPLL with 97fs rms Jitter, -120dBc/Hz PN at 1MHz Offset, and With Retrace Time of 12.5ns and 2μs Chirp Settling Time,” ISSCC, pp. 146-147, Feb. 2022 \
> [3] Z. Shen et al., “A 24GHz Self-Calibrated ADPLL-Based FMCW Synthesizer with 0.01% rms Frequency Error Under 3.2GHz Chirp Bandwidth and 320MHz/μs Slope,” ISSCC, pp.450-451, Feb. 2021.
> 
> *piecewise-linear digital predistortion (PWL-DPD)* \
> [1] \
> [4] P. T. Renukaswamy et al., “A 16GHz, 41kHzrms Frequency Error, Background-Calibrated, Duty-Cycled FMCW Charge-Pump PLL,” ISSCC, pp. 74-75, Feb. 2023. \
> [5] Q. Shi et al., “A Self-Calibrated 16GHz Subsampling-PLL-Based 30μs Fast Chirp FMCW Modulator with 1.5GHz Bandwidth and 100kHz rms Error,” ISSCC, pp. 408-409, Feb. 2019.
> 
> *varactor driven by a DAC :  [4, 5]* \
> 
> *digital skew calibration algorithm* \
> [6] G. Marzin et al., “A 20 Mb/s Phase Modulator Based on a 3.6 GHz Digital PLL With −36 dB EVM at 5 mW Power,” IEEE JSSC, vol. 47, no. 12. pp. 2974-2988, Dec. 2012.
> 
> *classical LMS calibration :  [1]* \