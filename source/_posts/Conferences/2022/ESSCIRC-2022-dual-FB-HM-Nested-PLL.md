---
title: ESSCIRC-2022 An Inductorless Fractional-N PLL Using Harmonic-Mixer-Based Dual Feedback and High-OSR Delta-Sigma-Modulator with Phase-Domain Filtering
toc: true
tags:
  - ESSCIRC
  - 2022
  - TokyoU
  - PLL
  - RO
abbrlink: 17902
date: 2023-02-11 22:50:48
---

![Keypoints](https://api2.mubu.com/v3/document_image/291c6c03-928b-4c8d-918c-c507a0436e23-216525.jpg) \

##### Full Citation

M. Osada, Z. Xu and T. Iizuka, "**An Inductorless Fractional-N PLL Using Harmonic-Mixer-Based Dual Feedback and High-OSR Delta-Sigma-Modulator with Phase-Domain Filtering**," ESSCIRC 2022- IEEE 48th European Solid State Circuits Conference (ESSCIRC), Milan, Italy, 2022, pp. 245-248, doi: 10.1109/ESSCIRC55480.2022.9911315.

[IEEE Link](https://ieeexplore.ieee.org/document/9911315) \

## Keypoints

- harmonic-mixer-based main loop
  - dominant the main BW and stability
  - wide BW to suppress RO PN
- nested PLL
  - split as two dividers
  - high DSM frequency
  - narrow BW to filter DSM QN
  - attenuate noise contribution
- aux PLL: SPD and wide BW

## Background

- conflict BW requirement
  - wide BW to suppress RO PN
  - narrow BW to filter out DSM QN
- cancel DSM QN with DTC
  - need gain/linearity calibration
- HM-based PLL
  - intrinsic unity FB gain by freq subtraction
  - no noise amplification
  - but limited by low DSM freq
    - stability
    - hard to filter out harmonics

![The proposed architecture and its noise suppression mechanism](https://api2.mubu.com/v3/document_image/0a3a3c64-435d-48e0-b6a8-4944bcf118b6-216525.jpg) \

## Conclusion

**TECH**  65 nm \
**REF**  50 MHz \
**OUT**  2.98~3.5 GHz \
**REF SPUR**  -67 dBc \
**FRAC SPUR** -53 dBc \
**POWER**  14.83 mW \
**RMS JITTER**  1079 fs \
**FOM** -227.6 dB \

## Important Reference

> *Sample-and-Hold (S/H) based HMs* \
> [4] D. Yang et al., ”16.6 A Calibration-Free Triple-Loop Bang-Bang PLL Achieving 131fsrms Jitter and-70dBc Fractional Spurs,” 2019 IEEE International Solid- State Circuits Conference - (ISSCC), 2019, pp. 266-268, doi: 10.1109/ISSCC.2019.8662494.
>
> \------------------
>
> *Dual Feedback* \
> [5] M. Osada, Z. Xu and T. Iizuka, ”A 3.2-to-3.8 GHz Harmonic-Mixer-Based Dual-Feedback Fractional-N PLL Achieving -65 dBc In-Band Fractional Spur,” in IEEE Solid-State Circuits Letters, vol. 3, pp. 534-537, 2020, doi: 10.1109/LSSC.2020.3037311.
>
> [6] M. Osada, Z. Xu and T. Iizuka, ”A 3.2-to-3.8GHz Calibration-Free Harmonic-Mixer-Based Dual-Feedback Fractional-N PLL Achieving –66dBc Worst-Case In-Band Fractional Spur,” 2020 IEEE Symposium on VLSI Circuits, 2020, pp. 1-2, doi: 10.1109/VLSICircuits18222.2020.9162799.
>
> \------------------
>
> [7] D. Yang, D. Murphy, H. Darabi, A. Behzad, R. Ruby and R. Parker, ”An FBAR Driven -261dB FOM Fractional-N PLL,” 2021 IEEE Radio Frequency Integrated Circuits Symposium (RFIC), 2021, pp. 147-150, doi:10.1109/RFIC51843.2021.9490409.
>
> [8] D. Yang et al., “A Sub-100MHz Reference-Driven 25-to-28GHz Fractional-N PLL with -250dB FoM,” 2022 IEEE International Solid-State Circuits Conference (ISSCC), 2022, pp. 384-386.
>
> \------------------
>
> *sampling action in HM PLL* \
> [9] T. Iizuka and A. A. Abidi, “FET-R-C Circuits: A Unified Treatment—Part I: Signal Transfer Characteristics of a Single-Path,” in IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 63, no. 9, pp. 1325-1336, Sept. 2016.
>
> \------------------
>
> original nested HM-based PLL \
> [10] P. Park, D. Park and S. Cho, ”A 2.4 GHz Fractional-N Frequency Synthesizer With High-OSR ∆Σ Modulator and Nested PLL,” in IEEE Journal of Solid-State Circuits, vol. 47, no. 10, pp. 2433-2443, Oct.2012, doi: 10.1109/JSSC.2012.2209809.
