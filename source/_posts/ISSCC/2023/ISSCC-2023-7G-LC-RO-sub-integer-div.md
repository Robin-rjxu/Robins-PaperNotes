---
title: ISSCC-2023 A 135fsrms-Jitter 0.6-to-7.7GHz LO Generator Using a Single LC-VCO-Based Subsampling PLL and a Ring-Oscillator-Based Sub-Integer-N Frequency Multiplier
toc: true
tags:
  - ISSCC
  - 2023
  - KAIST
  - PLL
abbrlink: 54004
date: 2023-02-24 21:56:41
---

![Keypoints](https://api2.mubu.com/v3/document_image/d064aae4-e44c-482e-bb73-950cfd71bfcd-216525.jpg) \

##### Full Citation

Yongwoo Jo, et al, "**A 135fsrms-Jitter 0.6-to-7.7GHz LO Generator Using a Single LC-VCO-Based Subsampling PLL and a Ring-Oscillator-Based Sub-Integer-N Frequency Multiplier**,"

## Keypoints

- cascaded PLL
  - 2nd-stage : sub-integer(0.25) RO-based FM
    - wide loop bandwidth to suppress PN
    - phase-rotating divider (PRD)
    - individual-delay-cell-controllable (IDC)-DLF to QE cali
  - 1st-stage : low-PN LC SSPLL (narrow FTR ~ 21 %)
    - VDAC for 3rd-order QE cali
    - polynomial with 4 coefficients

## Background

- FR1 is still primary spectrum for 5G
  - ever-expanding range of FR1 (0.6 - 7.1 GHz)
  - low IPN (integrated phase noise (PN)) to support high-order QAMs
  - accurate quadrature phases
- cascade PLL archietecture
  - 1st-stage : low-PN frac LC SSPLL
  - 2nd-stage : RO based frequency multiplier
  - high-freq and long DIV chain ==> area and power ++
  - wide FTR ==> low-Q ==> low PN or high power
- second-order curve fitting
  - need 3 coefficients for each of 8 bins

<img src="https://api2.mubu.com/v3/document_image/fda8e835-9070-40f2-9b0b-84213cc6504f-216525.jpg" width = "500" alt="The proposed LO Generator" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  150 MHz \
**OUT**  0.6 - 7.7 GHz \
**REF SPUR**  -77 dBc \
**FRAC SPUR**  -66 dBc \
**POWER**  17.9 mW \
**RMS JITTER**  135 fs \
**FOM**  -244.9 dB \

## Important References

> *second-order curve fitting* \
> [6] J. Kim et al., “A 104fsrms-Jitter and −61dBc-Fractional Spur 15GHz Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error Cancelation Technique,” ISSCC, pp. 448−449, Feb. 2021.

