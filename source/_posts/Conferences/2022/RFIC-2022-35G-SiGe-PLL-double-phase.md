---
title: >-
  RFIC-2022 A 59-fs-rms 35-GHz PLL with FoM of −241-dB in 0.18−μm BiCMOS/SiGe
  Technology
toc: true
tags:
  - RFIC
  - 2022
  - UofUtah
  - PLL
abbrlink: 44465
date: 2023-03-12 17:23:46
---

![Keypoints](https://api2.mubu.com/v3/document_image/ece41c07-454b-4894-93a2-0e1df899dd38-216525.jpg) \

##### Full Citation

R. Bindiganavile, A. Wahid, J. Atkinson and A. Tajalli, "**A 59-fs-rms 35-GHz PLL with FoM of −241-dB in 0.18−μm BiCMOS/SiGe Technology**," 2022 IEEE Radio Frequency Integrated Circuits Symposium (RFIC), Denver, CO, USA, 2022, pp. 163-166, doi: 10.1109/RFIC54546.2022.9863116.

[IEEE Link](https://ieeexplore.ieee.org/document/9863116) \

## Keypoints

- extend loop BW with minimal jitter peaking
  - double-phase PFD
  - high frequency reference
  - correct duty-cycle distortion (DCD)
    by tuning input buffer bias
- start-up
  - 8b R-2R DAC initialize VCO Vctrl
  - after a delay then activate PFD+CPC

## Background

- applications : 5G, ADC, MIMO
  - require high-freq clock with high purity
  - deliver high power
  - integrate PA and LO in SiGe
    higher breakdown voltage and fT
- ultra low in-band noise and intg jitter
  - low-PN VCO
  - wide PLL BW

<img src="https://api2.mubu.com/v3/document_image/8bef1b90-9c67-49dc-bd3b-71fcb4dc6132-216525.jpg" width = "500" alt="Topology of the proposed matrix PLL with added programmability and calibration" align=center />

## Conclusion

**TECH**  0.18 um SiGe \
**REF**  1000 MHz \
**OUT**  34 - 37 GHz \
**REF SPUR**  -48.56 dBc \
**POWER**  195 mW  \
**RMS JITTER**  59 fs \
**FOM**  -241.6 dB \

## Important References

> *multiple phases for phase adjustment* \
> [11] A. Tajalli, “Matrix phase detector for high bandwidth and low jitter frequency synthesis," in Elect. Let., vol. 53, no. 15, 2017.
