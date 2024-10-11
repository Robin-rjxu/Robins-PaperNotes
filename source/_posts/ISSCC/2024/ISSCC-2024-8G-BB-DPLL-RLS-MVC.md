---
title: >-
  ISSCC-2024 10.2 A 5.5μs-Calibration-Time, Low-Jitter, and Compact-Area
  Fractional-N Digital PLL Using the Recursive-Least-Squares (RLS) Algorithm 
toc: true
tags:
  - ISSCC
  - 2024
  - DPLL
  - BBPD
  - DTC
  - RLS
  - KAIST
abbrlink: 50215
date: 2024-10-11 19:52:00
---

![Keypoints](https://s21.ax1x.com/2024/10/11/pAY1fRx.png) \

##### Full Citation

S. Jang, M. Chae, H. Park, C. Hwang and J. Choi, "**10.2 A 5.5μs-Calibration-Time, Low-Jitter, and Compact-Area Fractional-N Digital PLL Using the Recursive-Least-Squares (RLS) Algorithm**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 190-192, doi: 10.1109/ISSCC49657.2024.10454495.

[IEEE Link](https://ieeexplore.ieee.org/document/10454495) \

## Keypoints

- fast-converging DCD-RLS MVC
  - dichotomous-coordinate-descent (DCD)-algorithm-based iterative  process
  - on-chip implementation of the RLS-based MVC
- fast settling BB-DPLL
  - type-II gear shifting (GS)
  - 3 aux TDCs with different threshold
- low jitter
  - wide loop BW
  - jitter reduction
    - DTC cancels DSM QN
    - DTC range reduction with PSEL
    - MVC cancels various circuit NLs
- DCD-RLS MVS
  - xn-vector generator (XVG)
  - hn-vector generator (HVG)
  - predistortion-code generator (PCG)
  - find approx. hn
    - iterative process based on DCD (3-steps)
    - solve the Auxiliary Normal Equation
  - 5-track DSM

## Background

- low jitter PLL
  - narrow loop BW
    - suppress in-band noise
    - low-PN LC VCO is vital, like multicore LC VCO
  - wide loop BW
    - rely on removing in-band noise
    - cancel Q-noise with DTC
    - reduce DTC range with PSEL (phase selector) and MMD
- multivariable calibration (MVC)
  - DTC gain
  - compensate DTC nonlinearity
  - convergence time grows exponentially
  - LMS-based MVC
    - fixed updating steps mu
    - without considering correlations between inputs
      - calibrations can interfere and race
      - set mu sufficiently different from each other
        - less mutual interference
        - increase overall calibration time due to sluggish settling
    - simple hardware
      - only  ADD and MULT
- RLS-based MVC
  - find all variable collectively
  - correlation matrix Rn instead of fixed mu
    - reflect the correlations between inputs (auto- and cross-)
    - convergence time can be reduced significantly
  - complex hardware
    - need to solve Normal Equation
    - involves Matrix Inversion
    - need DIV and many MULT


<img src="https://s21.ax1x.com/2024/10/11/pAY1WJ1.png" width = "500" alt="Overall architecture of the fractional-N DPLL" align=center />

<img src="https://s21.ax1x.com/2024/10/11/pAY1IsO.png" width = "500" alt="Problem of a typical LMS-based MVC and principle of an RLS-based MVC" align=center />

<img src="https://s21.ax1x.com/2024/10/11/pAY15QK.png" width = "500" alt="Schematics of the proposed DCD-RLS MVC " align=center />

## Conclusion

**TECH**  40 nm \
**REF**  100 MHz \
**OUT**  6.4~8.2 GHz \
**REF SPUR**  -64 dBc \
**FRAC SPUR**  -68 dBc \
**POWER**  15.7 mW  \
**RMS JITTER**  88 fs \
**FOM**  -249.1 dB \

## Important References

> *multicore LC VCOs* \
> [1] E. Thaller et al., “A K-Band 12.1-to-16.6GHz Subsampling ADPLL with 47.3fsrms Jitter Based on a Stochastic Flash TDC and Coupled Dual-Core DCO in 16nm FinFET CMOS,” ISSCC, pp. 452-453, Feb. 2021. \
> [2] W. Wu et al., “A 14-nm Ultra-Low Jitter Fractional-N PLL Using a DTC Range Reduction Technique and a Reconfigurable Dual-Core VCO,” IEEE JSSC, vol. 56, no. 12, pp. 3756-3767, Dec. 2021. \
> *(DTC range reduction)*
> 
> *DTC cancels DSM QN* \
> [3] H. Park et al., “A 365fsrms-Jitter and -63dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/Third-Order Nonlinearity Cancelation and a Probability-Density-Shaping ΔΣM,” ISSCC, pp. 442-443, Feb. 2021.
> 
> *type-II gear shift* \
> [4] S. M. Dartizio et al., “A 68.6fsrms-Total-Integrated-Jitter and 1.56μs-Locking-Time Fractional-N Bang-Bang PLL Based on Type-II Gear Shifting and Adaptive Frequency Switching,” ISSCC, pp. 386-387, Feb. 2022.
> 
> [5] Z. Gao et al., “A 2.6-to-4.1GHz Fractional-N Digital PLL Based on a Time-Mode Arithmetic Unit Achieving -249.4dB FoM and -59dBc Fractional Spurs,” ISSCC, pp. 380-381, Feb. 2020.
> 
> *solve the Auxiliary Normal Equation* \
> [6] Y. Zakharov et al., “Low-Complexity RLS Algorithms Using Dichotomous Coordinate Descent Iterations,” IEEE Trans. Signal Process., vol. 56, no. 7, pp. 3150-3161, July. 2008.
> 
> *TDC aux path for frequency acquisition* \
> [7] L. Bertulessi et al., “A Low-Phase-Noise Digital Bang-Bang PLL with Fast Lock over a Wide Lock Range,” ISSCC, pp. 252-253, Feb.