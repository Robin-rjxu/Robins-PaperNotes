---
title: >-
  CICC-2024 A 66.7fs-Integrated-Jitter Fractional-N Digital PLL Based on a
  Resistive-Inverse-Constant-Slope DTC
toc: true
tags:
  - CICC
  - 2024
  - DPLL
  - BBPD
  - DTC
  - Milano
abbrlink: 43863
date: 2024-11-12 16:59:08
---

![Keypoints](https://s21.ax1x.com/2024/11/12/pAcRZ2q.png) \

##### Full Citation

P. Salvi et al., "**A 66.7fs-Integrated-Jitter Fractional-N Digital PLL Based on a Resistive-Inverse-Constant-Slope DTC**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529003.

[IEEE Link](https://ieeexplore.ieee.org/document/10529003) \

## Keypoints

- resistor-based inverse-constant-slope DTC (R-ICS DTC)
  - current generators (CGs)are replaced with resistors
    - flicker noise is ideally avoided
    - the white noise contribution is reduced
    - power consumption and noise are totally avoided
  - linearity
    - current charging C becomes more voltage-dependent
    - retains the same immunity of the ICS
    - does not degrade the DTC linearity  
  - operation
    - pre-charge duration
    - set through the pre-charge generator (PG)
    - as a multiple of the digitally-controlled oscillator (DCO) period
  - circuits
    - front-end circuit
      - generate the signals triggering the DTC
      - reset the capacitor
    - core circuit
      - adopts resistors in place of CGs
      - cascoded output buffer
        - reduce the cross-conduction current
        - improving both noise and power consumption
      - pull-up circuit
        - forcing the DTC to always sink the same charge from the supply
        - reduces the memory effects
        - avoid code-dependent supply fluctuations
- frac-N BB-DPLL
  - DTC-range-reduction technique
    - the multiplexer (MUX) and flip-flop (FF) stages are cascaded to the PG
    - MUX driving signal S[k] is also added to the PG input code
    - shift input in_pch by the same Tdco/2 delay
  - coarse R-ICS DTC
    - higher K value is enabled due to range reduction
  - fine DTC
    - variable-slope
    - cancel the residual quantization error
    - negligible non-linearity
  - calibration
    - coarse/fine gain calibration : 2 LMS
    - DTC precharge and input DCC : 2 LMS
  - (FCW subtractive dithering technique)

## Background

- low-jitter local oscillators for wireless systems
  - fractional-N PLLs  dithering the modulus control of the frequency divider in feedback
  - digital-to-time converter (DTC) to cancel-out the quantization-error (QE)
    - DTC non-linearity distorts the QE sequence
    - significant fractional spurs 
    - limited spectral purity and jitter
- inverse-constant-slope DTC (ICS-DTC)
  - larger DTC jitter caused by the current generators (CGs)
  - very linear
  - immunity to both nonlinearity from
    - charging current
    - capacitance dependencies
  - generated delay Tdtc is proportional to Tpch
  - operation with 2 phases
    - phase 1 
      - controlling the time interval Tpch
      - regulates the voltage Vpch stored in C
    - phase 2
      - scaling by a factor K the current charging C
      - voltage V reaches the output-buffer threshold Vth
  - limitations
    - needs a bias branch, increasing power and noise
    - large flicker and white noise from the current generators (CGs)

<img src="https://s21.ax1x.com/2024/11/12/pAcREPs.png" width = "500" alt="Implemented BBPLL with R-ICS DTC and range-reduction technique" align=center />

<img src="https://s21.ax1x.com/2024/11/12/pAcRVGn.png" width = "500" alt="Conventional ICS-DTC and presented R-ICS DTC" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  125 MHz \
**OUT**  8.75 ~ 10.25 GHz \
**REF SPUR**  -75.8 dBc \
**FRAC SPUR**  -63.8 dBc \
**POWER**  16.7 mW  \
**RMS JITTER**  66.7 fs \
**FOM**  -251.3 dB \

## Important References

> *The inverse-constant-slope DTC (ICS-DTC)* \
> [1] S. M. Dartizio et al., "A 76.7fs-lntegrated-Jitter and −71.9dBc In-Band Fractional-Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering", ISSCC, 2023.
> 
> *DTC-range-reduction technique* \
> [2] W. Wu et al., "A 14nm Analog Sampling Fractional-N PLL with a Digital-to-Time Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs at Near-Integer Channels," ISSCC, 2021.
> 
> *cascoded output buffer* \
> [3] J. Ru et al., “A High-Linearity Digital-to-Time Converter Technique: Constant-Slope Charging”, JSSC, 2015.
> 
> *digital-to-time converter (DTC) to cancel-out the quantization-error (QE) : [1, 2, 4, 5]* \
> [4] D. Xu et al., "A 6.5-to-8GHz Cascaded Dual-Fractional-N Digital PLL Achieving -63.7dBc Fractional Spurs with 50MHz Reference", CICC, 2023. \
> [5] G. Castoro et al., "A 9.25GHz Digital PLL with Fractional-Spur Cancellation Based on a Multi-DTC Topology", ISSCC, 2023.