---
title: >-
  ISSCC-2023 A 76.7fs-Integrated-Jitter and -71.9dBc In-Band Fractional-Spur
  Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW
  Subtractive Dithering
toc: true
tags:
  - ISSCC
  - 2023
  - Polimi
  - PLL
  - DTC
abbrlink: 36063
date: 2023-02-21 00:28:33
---

![Keypoints](https://api2.mubu.com/v3/document_image/190c2023-8375-478e-8447-7067574cdac9-216525.jpg) \

##### Full Citation

Simone M. Dartizio, el al, "**A 76.7fs-Integrated-Jitter and -71.9dBc In-Band Fractional-Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering**," \

## Keypoints

- coarse inverse constant-slope DTC
  - the current scaling factor K is voltage independent
  - the sum Tpch + K·Tdtc is constant
    the integral of C(V)/I’G(V) between two fixed bounds, 0 and Vth
  - Tdtc has a linear dependence on the accurate Tpch time interval
  - precharged by Tpch (tres_pch over Tdco)
  - Tres_dtc scaled by current factor K
- fine variable-slope DTC
  narrow range and high linearity
- FCW subtractive dithering
  - FCW is offset (scrambled) by a non-zero-average random sequence
  - the induced phase-error is corrected
    cancelled out by shifting both the inpch and indtc signals in steps of 0.5·Tdco

## Background

- BBPD PLL
  - good jitter performance
  - narrow linear input range
- fractional operation
  - DTC compensate Q-error
- DTC non-linearity
  - Q-error follows a pattern with a period of (1/FCW_frac) cycles
  - generate significant fractional spurs
  - improving the DTC linearity
    - constant slope DTC (CS-DTC)
    - voltage sensitivity of current generators (CGs)
    - nonlinear DAC
  - suitable randomization of the Q-error
    - higher quantization-noise power
    - larger random jitter
    - wider range needed for the DTC

<img src="https://api2.mubu.com/v3/document_image/dd080d8c-16d7-4edc-a5cc-118dcd99e598-216525.jpg" width = "500" alt="Proposed BBPLL with Inverse-CS-DTC and Subtractive FCW dithering" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  9.25 ~ 10.5 GHz \
**REF SPUR**  -70.5 dBc \
**FRAC SPUR**  -71.9 dBc \
**POWER**  17.2 mW \
**RMS JITTER**  75.9 fs \
**FOM**  -250 dB \

## Important References

> *Highly linear constant-slope DTC* \
> [2] J. Ru et al., “A High-Linearity Digital-to-Time Converter Technique: Constant-Slope Charging,” IEEE JSSC, vol. 50, no. 6, pp. 1412-1423, June 2015.
>
> *Randomize but increase jitter* \
> [3] H. Park et al., “A 365fsrms-Jitter and -63dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/Third-Order Nonlinearity Cancellation and a Probability-Density-Shaping ΔΣM,” ISSCC, pp. 442-443, Feb. 2021. \
> [4] E. Familier et al., “Second and Third-Order Successive Requantizers for Spurious Tone Reduction in Low-Noise Fractional-N PLLs,” IEEE CICC, pp. 1-4, May 2017.
