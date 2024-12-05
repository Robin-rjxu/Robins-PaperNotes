---
title: ESSERC-2024 A 7.2G-16GHz ADPLL based on a single-core dual-mode DCO
toc: true
tags:
  - ESSERC
  - 2024
  - DCO
  - DPLL
  - PKU
abbrlink: 61854
date: 2024-12-05 14:35:43
---

![Keypoints](https://s21.ax1x.com/2024/12/05/pATFcpn.png) \

##### Full Citation

N. Zhang, S. Zhang, F. Yang, Y. Wang, J. Liu and H. Liao, "**A 7.2G-16GHz ADPLL based on a single-core dual-mode DCO**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 117-120, doi: 10.1109/ESSERC62670.2024.10719581.

[IEEE Link](https://ieeexplore.ieee.org/document/10719581) \

## Keypoints

- single-core dual-mode digital controlled oscillator (DCO)
  - two frequency bands
  - controlled by GM1 and GM2
  - principle
    - Parallel-Mode and Series-Mode
    - switch by GM1/GM2
    - different current direction
    - no Q factor degeneration
    - larger k
      - large inductance switching
      - two resonance impedance peaks closer to each other
    - two resonant peaks for each mode
      - the same resonant frequencies
      - different resonant impedances of Z11 and Z22 
      - Parallel-Mode --> high freq.
      - Series-Mode --> low freq.
- ADPLL based on the dual-mode DCO
  - single-core dual-mode wide tuning range DCO
    - 6.3G-10.7GHz and 10.0G-16.8GHz 
    - coarse/fine switch-cap array
    - 10b DAC controlled varactors
  - 8-divider(DIV8)
    - injection-locked ring oscillator structure
  - multi modules divider (MMD) with retiming
    - replaced the output rising edge of MMD with DIV8
  - Vernier Time-Digital Converter (TDC)
    - two delay lines of REF and DIV
    - 1 ps resolution
  - Type-II digital loop filter (DLF)

## Background

- wireless communication
  - variable applications
    - 5G NR communication systems
    - several bands in mmW frequencies(>24GHz)
    - Satellite mobile communications use K/Ka band
  - broad range of frequency bands
    - ADPLL with a tuning range greater than 67%
    - full spectrum with only div-2s or mulp-2s
  - for high-speed
    - low-phase noise
    - sub 100 fs
- wide-range LC oscillators
  - Multi-DCOs or frequency dividers
    - large area
    - system complexity
    - layout difficulties
  - Multi-core DCOs
    - high power consumption
    - large KDCO variations
    - 
  - Transformer-based resonance-mode-switching DCOs 
    - wide frequency tuning range (FTR)
    - intricate to design
    - hard to implement the inner coil
      - at increasing frequency 
      - limited physical size
      - k value constraint

<img src="https://s21.ax1x.com/2024/12/05/pATFrkQ.png" width = "500" alt="Block diagram of the proposed ADPLL" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pATFsYj.png" width = "500" alt="Work Principle and Equivalent Circuits of the proposed DCO" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pATFyfs.png" width = "500" alt="Detailed circuits implementation and simulation results" align=center />

## Conclusion

**TECH**  40 nm \
**REF** 200 MHz \
**OUT**  7.2 ~ 15 GHz (76%) \
**POWER**  18.9 mW  \
**RMS JITTER**  103.8 fs \
**FOM**  -245.7 dB \

## Important References

> *Transformer-based resonance-mode-switching DCOs with greater than 67% FTR* \
> [1] G. Li, L. Liu, Y. Tang and E. Afshari, "A Low-Phase-Noise Wide-Tuning-Range Oscillator Based on Resonant Mode Switching," in IEEE Journal of Solid-State Circuits, vol. 47, no. 6, pp. 1295-1308, June 2012.
> 
> *limited physical size and k value* \
> [2] Y. Wang et al., "Analysis and Design of a Dual-Mode VCO With Inherent Mode Compensation Enabling a 7.9–14.3-GHz 85-fs-rms Jitter PLL," in IEEE Journal of Solid-State Circuits, vol. 58, no. 8, pp.2252-2266, Aug. 2023.
> 
> *high-frequency DPLL* \
> [3] W. Tao, W. Zhao, R. B. Staszewski, F. Lin and Y. Hu, "An 18.8-to-23.3 GHz ADPLL Based on Charge-Steering-Sampling Technique Achieving 75.9 fs RMS Jitter and –252 dB FoM," 2023 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Kyoto, Japan, 2023, pp. 1-2. \
> [4] L. Zhang and A. Niknejad, "A 480-Multiplication-Factor 13.2-to-17.3GHz Sub-Sampling PLL Achieving 6.6mW Power and -248.1 dB FoM Using a Proportionally Divided Charge Pump," 2022 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 1-3. \
> [5] J. Du et al., "A Millimeter-Wave ADPLL With Reference Oversampling and Third-Harmonic Extraction Featuring High FoMjitter-N," in IEEE Solid-State Circuits Letters, vol. 4, pp. 214- 217, 2021. \
> [6] S. Ek et al., "A 28-nm FD-SOI 115-fs Jitter PLL-Based LO System for 24–30-GHz Sliding-IF 5G Transceivers," in IEEE Journal of Solid-State Circuits, vol. 53, no. 7, pp. 1988-2000, July 2018. \
> [7] M. Raj, A. Bekele, D. Turker, P. Upadhyaya, Y. Frans and K. Chang, "A 164fsrms 9-to-18GHz sampling phase detector based PLL with in-band noise suppression and robust frequency acquisition in 16nm FinFET," 2017 Symposium on VLSI Circuits, Kyoto, Japan, 2017, pp. C182-C183.