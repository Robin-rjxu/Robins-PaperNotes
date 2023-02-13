---
title: >-
  ISSCC-2021 A Fractional-N Digital MDLL with Background Two-Point DTC
  Calibration Achieving -60dBc Fractional Spur
toc: true
tags:
  - ISSCC
  - 2021
  - USC
  - MDLL
abbrlink: 60587
date: 2023-02-13 22:35:48
---

![Keypoints](https://api2.mubu.com/v3/document_image/93dbbcb6-05f7-4140-b314-fcabecf85c4a-216525.jpg) \

##### Full Citation

Q. Zhang, S. Su, C. -R. Ho and M. S. -W. Chen, "**29.4 A Fractional-N Digital MDLL with Background Two-Point DTC Calibration Achieving -60dBc Fractional Spur**," 2021 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2021, pp. 410-412, doi: 10.1109/ISSCC42613.2021.9365819.

[IEEE Link](https://ieeexplore.ieee.org/document/9365819) \

## Keypoints

- accurately control inj timing in frac MDLL to reduce spurs
- 2-point calibration for DTC gain and offset
  - simultaneously est gain and offset by occasional inj squelching
  - correct in both analog(gain) and digital domains(offset)
  - use TDC dithering to improve accuracy
  - adaptive comb-filter-assisted cancellation loop to remove dithering err.

## Background

- frac MDLL
- injection timing must drift away
  - use DTC: offset and gain errors can introduce spurs

![Overall of the MDLL with 2-point DTC cali](https://api2.mubu.com/v3/document_image/a5ffcf86-4635-4ba3-b51c-49b1699b70b2-216525.jpg) \

## Conclusion

**TECH**  65 nm \
**REF**  50 MHz \
**OUT**  1.5 GHz \
**REF SPUR**  -43 dBc \
**FRAC SPUR**  -52 dBc \
**POWER**  11.95 mW @ 1 V \
**RMS JITTER**  1690 fs \
**FOM**  -224.8 dB \

## Important References

> *uses TDC dithering to enhance error estimation accuracy* \
> [4] C.-R. Ho et al., “A Fractional-N Digital PLL with Background-Dither-Noise-Cancellation Loop Achieving <-62.5dBc Worst-Case Near-Carrier Fractional Spurs in 65nm CMOS,” ISSCC, pp. 394-395, 2018.
