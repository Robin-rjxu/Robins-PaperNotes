---
title: >-
  ISSCC-2022 A 68.6fsrms-total-integrated-jitter and 1.56μs-locking-time
  fractional-N bang-bang PLL based on type-II gear shifting and adaptive
  frequency switching
toc: true
tags:
  - ISSCC
  - 2022
  - Polimi
  - PLL
  - BBPD
abbrlink: 49830
date: 2023-03-06 23:45:59
---

![Keypoints](https://api2.mubu.com/v3/document_image/e4102565-06e2-4641-816b-2ab4937b242e-216525.jpg) \

## Full Citation

S. M. Dartizio et al., "**A 68.6fsrms-total-integrated-jitter and 1.56μs-locking-time fractional-N bang-bang PLL based on type-II gear shifting and adaptive frequency switching**," 2022 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 1-3, doi: 10.1109/ISSCC42614.2022.9731683.

[IEEE Link](https://ieeexplore.ieee.org/document/9731683) \

## Keypoints

- improve jitter and locking time trade-off of BB-DPLLs
  - type-II gear shifting
    - increase P/I parameters during freq transient
    - bring them back to the value for minimal jitter at steady state
  - adaptive frequency-switching (AFS)
    - on-the-fly estimation of DCO gain
    - switch PLL freq to a coarse estimation to of the target
    - linear estimation without training sequence in LMS
  - fast locking with the knowledge of ΔFCW and M=Fc/Fref
    - ΔFCW varies in different tuning state
    - step-up pulse on coarse tuning of DCO
    - step-up stairs on FCW
    - count the number of period until detected polarity switching back
    - the number is proportional to M
- BB-DPLLs architecture
  - 2 extra BBPDs
    - coarse BBPD
    - fine BBPD
  - start-stop scheme
    - monitor fine-BBPD threshold crossing
    - prevent interaction between loops
    - scale up to large and back by a factor of 2
    - set optimal prop/intg ratio during shift
      equivalent to independent prop/intg shift


## Background

- BBPD has inability to quickly recover from freq jump due to limited linear range
- wide-range TDC can solve relocking issue
  - requires large area and high power
  - limited jitter performance due to finite quantization resolution
- auxiliary frequency-acquisition loops
  - need extra BBPDs
  - aux loop with larger loop gain than the main loop
  - large gain causes nonlinearity
    - introduces unwanted dependency among loops
    - limits locking time

<img src="https://api2.mubu.com/v3/document_image/c17ba2c0-44f1-4149-bcc0-be811942d07e-216525.jpg" width = "500" alt="Block diagram of the implemented BBPLL (upper part) and the high-level operation of the AFS and type-II GS techniques (bottom part)" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  8.5 - 10 GHz \
**REF SPUR**  -70.2 dBc \
**FRAC SPUR**  -58.2 dBc \
**POWER**  20 mW  \
**RMS JITTER**  57.2 fs \
**FOM**  -251.8 dB \

## Important References

> *BBPD DPLL capable of fast locking* \
> [1] A. Santiccioli et al., “A 66fsrms Jitter 12.8-to-15.2GHz Fractional-N Bang-Bang PLL with Digital Frequency-Error Recovery for Fast Locking” ISSCC, pp. 268-270, Feb. 2020.
> 
> *auxiliary frequency-acquisition loops* [1,4,5] \
> [4] L. Bertulessi et al., “A Low-Phase-Noise Digital Bang-Bang PLL with Fast Lock over a Wide Lock Range”, ISSCC, pp. 252-254, Feb. 2018. \
> [5] C. Tsai et al., “Analysis of a 28-nm CMOS Fast-Lock Bang-Bang Digital PLL with 220-fs rms Jitter for Millimeter-Wave Communication,” IEEE JSSC, vol. 55, no. 7, pp.1854-1863, July 2020.
> 
> *cancel dead zone* [4]
>
> *previous gear shift [5] LMS loop for DCO gain estimation needing a training sequence* 
