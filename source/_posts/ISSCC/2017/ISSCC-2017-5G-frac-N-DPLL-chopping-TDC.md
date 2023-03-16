---
title: >-
  ISSCC-2017 24.8 A 14nm fractional-N digital PLL with 0.14psrms jitter and
  −78dBc fractional spur for cellular RFICs
toc: true
tags:
  - ISSCC
  - 2017
  - samsung
  - PLL
abbrlink: 6730
date: 2023-03-16 23:38:38
---

![Keypoints](https://api2.mubu.com/v3/document_image/065073a2-0911-4989-8e75-5da5a38b3ae1-216525.jpg) \

##### Full Citation

C. -W. Yao et al., "**24.8 A 14nm fractional-N digital PLL with 0.14psrms jitter and −78dBc fractional spur for cellular RFICs**," 2017 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2017, pp. 422-423, doi: 10.1109/ISSCC.2017.7870441.

[IEEE Link](https://ieeexplore.ieee.org/document/7870441) \

## Keypoints

- using wide-range TDC instead of DTC
  - offset cali
  - gain cali
    - coarse/fine matching
    - ADC margin for device mismatch
  - NL cali
- TDC chopping
  - converts both pos and neg phase errors
  - PFD --> up/dn --> pulse and polarity
  - a pair of sw conditionally reverses the in/out polarity
  - the noise is up-mixed to the sw freq
  - randomization from FB DSM
  - adjust div ratio to shift TDC inpu away from zero
  - with offset cancellation
- coarse/fine TDC
  - coarse conv with a 13-stage RO
    - reset RO every cycle
    - RO phases drive a counter
    - tres = Tro/13
  - fine-conv through SAR ADC
    - select two node voltages near zero-crossing point
    - conv. to digital by a 7b SAR ADC
    - tres = Tro/13/(V1-V2) ~ 0.2 ps
- TDC NL cali
  - frontend cali at power up
  - set a selected frac value
  - estimate TDC NL in 52 region
    similar to piece-wise cali

## Background

- high mobile data rate and advanced standards
  at 5G band, 256 QAM and 4x4 MIMO
  - IPN < -48 dBc
  - intg jitter < 155 fs
- GRO as noise shaped fine TDC
  - does not initialize the phase 
  - in integer mode, converts the same input in every clock cycle
  - generates periodic output
  - translates any non-ideality to spurs

<img src="https://api2.mubu.com/v3/document_image/f0542cd3-36fd-499b-a2ac-5ca7b1cfe313-216525.jpg" width = "700" alt="Digital PLL architecture and chopping TDC" align=center />

## Conclusion

**TECH**  14 nm \
**REF**  26 MHz \
**OUT**  2.690 GHz \
**REF SPUR**  -87.6 dBc \
**FRAC SPUR**  -78.6 dBc \
**POWER**  13.4 mW  \
**RMS JITTER**  137 fs \
**FOM**  -246 dB \

## Important References

> *previous digital frac-N DPLL using single-polar TDC* \
> [1] C. Yao and A. N. Willson, “A 2.8–3.2-GHz Fractional-N Digital PLL With ADC-Assisted TDC and Inductively Coupled Fine-Tuning DCO,” IEEE JSSC, vol. 48, no. 3, pp. 698-710, Mar. 2013.
> 
> *GRO* \
> [2] M. Z. Straayer and M. H. Perrott, “A Multi-Path Gated Ring Oscillator TDC with First-Order Noise Shaping,” IEEE JSSC, vol. 44, no. 4, pp. 1089-1098, Apr. 2009.
