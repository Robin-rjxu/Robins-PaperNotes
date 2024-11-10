---
title: >-
  CICC-2024 A 59.3fs Jitter and -62.1dBc Fractional-Spur Digital PLL Based on a
  Multi-Edge Power-Gating Phase-Detector
toc: true
tags:
  - CICC
  - 2024
  - PLL
  - DPLL
  - BBPD
  - DTC
  - Milano
abbrlink: 3790
date: 2024-11-11 07:23:37
---

![Keypoints](https://s21.ax1x.com/2024/11/11/pA6xXrD.png) \

##### Full Citation

S. M. Dartizio et al., "**A 59.3fs Jitter and -62.1dBc Fractional-Spur Digital PLL Based on a Multi-Edge Power-Gating Phase-Detector**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529002.

[IEEE Link](https://ieeexplore.ieee.org/document/10529002) \

## Keypoints

- multi-edge power-gating phase-detector (MEPG-PD)
  - phase-detector (PD)
    - gated bang-bang PDs (G-BBPDs)
      - gated-buffer (GB)
        - D is buffered and frozen upon the CK rising edge
        - avoid hold-time violations
        - reduce power
      - BBPD
    - power-gating oscillator (PGO)
  - aligning div_d to the closest osc_PG rising edge
    - PD selection logic
    - based on the quantization error from DSM
    - swapped even/odd output at PGO rising/falling
- calibration
  - period estimator (PE) : mapping PGO space to DCO period
  - phase-mismatch correction (PMC) : PGO stage delay mismatch
  - DTC gain calibration
- auxiliary oscillator in power-gating mode (denoted as PGO)
  - turned on for a T_w time-window
  - powering the PGO via a switch sw_PG
  - PGO edges are linearly spaced
  - T_PGO is smaller than T_w
  - aligning div_d to the closest osc_PG rising edge
- frac-N BB DPLL
  - phase-detector (PD)
  - digital loop filter (DLF)
  - power-gating oscillator (PGO)
    - 3-stage ring-oscillator (RO)
    - runs at 25GHz using minimum-length MOS
    - steep output voltage slope
    - noise can be minimized using a small Tw
    - required DTC range reduces to TPGO/6
    - preset output (0, 1, 0) for consistent startup
  - divider
  - 2nd-order MASH1-1

## Background

- wide data-rates wireless transceivers
  - ultra-low-jitter local-oscillators
- frac-N PLLs
  - DTC  to re-align the edges
    - nonlinearities
    - spurs
    - jitters
    - 
  - strong tradeoff
    - DTC range
    - linearity and jitter
  - DTC range reduction
    - only achieve 2x reduction


<img src="https://s21.ax1x.com/2024/11/11/pA6xjqe.png" width = "500" alt="Block diagram of the implemented PLL" align=center />

<img src="https://s21.ax1x.com/2024/11/11/pA6xOKO.png" width = "500" alt="Implementation of the circuits" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  8.75 ~ 10 GHz \
**REF SPUR**  -68.4 dBc \
**FRAC SPUR**  -62.1 dBc \
**POWER** 18.5 mW  \
**RMS JITTER**  59.3 fs \
**FOM**  -252.8 dB \

## Important References

> *DTC-based frac-N PLL* \
> [1] S. M. Dartizio et al., "A Low-Spur and Low-Jitter Fractional-N Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering", JSSC, 2023.
> 
> *reduce DTC range by 2x* \
> [2] W. Wu et al., "A 14-nm Ultra-Low Jitter Fractional-N PLL Using a DTC Range Reduction Technique and a Reconfigurable Dual-Core VCO," JSSC, 2021.
> 
> *DTC tradeoff of linearity and jitter /power :  [2-3] *\
> [3] D. Xu et al., "A 6.5-to-8GHz Cascaded Dual-Fractional-N Digital PLL Achieving -63.7dBc Fractional Spurs with 50MHz Reference," CICC, 2022
> 
> *power-gating oscillator* \
> [4] Y. Cho, et. al, "A 122fsrms-Jitter and −60dBc-Reference-Spur 12.24GHz MDLL with a 102 - Multiplication Factor Using a Power-Gating Technique," VLSI, 2023.