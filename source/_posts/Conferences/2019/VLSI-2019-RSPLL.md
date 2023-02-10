---
title: VLSI-2019-RSPLL
toc: true
abbrlink: 20694
date: 2023-02-10 20:35:55
tags:
  - VLSI
  - 2019
  - UMich
  - PLL
  - RO
---

![Keypoints](https://api2.mubu.com/v3/document_image/25e70618-0a81-4fb4-aacf-c1dffb1d9ffa-216525.jpg) \

##### Full Citation

J. -H. Seol, D. Sylvester, D. Blaauw and T. Jang, "**A Reference Oversampling Digital Phase-Locked Loop with -240 dB FOM and -80 dBc Reference Spur**," 2019 Symposium on VLSI Circuits, Kyoto, Japan, 2019, pp. C160-C161, doi: 10.23919/VLSIC.2019.8778010.

[IEEE Link](https://ieeexplore.ieee.org/document/8778010) \

## Keypoints
- oversample sinusoidal reference (RSPD) by DCO timing
  - time-interleaved RSPD
  - multiphase generator
    ｜ divided but retimed by DCO
- bang-bang PLL at every DCO cycle
  - AC coupling and CMP with Vref for the prop path
  - prop gain is set to be quadrature to the input (IDAC)
  - one of PD is used for the intg path
- a startup BB PLL

## Background

- PLL BW should be maximized to suppress RO PN
  - BW is limited by 1/10 Fref in conv. PLL
  - MDLL/ILCM have poor ref spur
- oversampling reference overcome the BW constraint

<img src="https://api2.mubu.com/v3/document_image/fd9ce19e-52fc-4a9f-8131-2d406c6f2762-216525.jpg" width = "500" alt="" align=center />

## Conclusion

**TECH** 28 nm \
**REF** 50 MHz \
**OUT** 2.0 GHz \
**REF SPUR** -80 dBc \
**POWER**  3.6 mW \
**RMS JITTER**  508 fs \
**FOM** -240.3 dB \

## Important References

> *reference buffer needed* \
> [4] J. Sharma and H. Krishnaswamy, “A dividerless reference-sampling RF PLL with −253.5dB jitter FOM and <-67dBc Reference Spurs,” in 2018 IEEE International Solid - State Circuits Conference - (ISSCC), Feb. 2018, pp. 258–260. doi: 10.1109/ISSCC.2018.8310282.

