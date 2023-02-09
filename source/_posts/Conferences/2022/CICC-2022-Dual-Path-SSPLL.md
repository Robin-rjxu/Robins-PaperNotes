---
title: >-
  CICC-2022 A 2-GHz Dual-Path Sub-Sampling PLL with Ring VCO Phase Noise
  Suppression
toc: true
tags:
  - CICC
  - 2022
  - PLL
  - RO
  - NYU
abbrlink: 40054
date: 2023-02-09 22:44:07
---

![Proposed Dual-Path SSPLL](https://api2.mubu.com/v3/document_image/ed692090-5368-4244-afa8-886ac6c86685-216525.jpg) \

##### Full Citation

Y. Dong, C. C. Boon, K. Yang and Z. Liu, "**A 2-GHz Dual-Path Sub-Sampling PLL with Ring VCO Phase Noise Suppression**," 2022 IEEE Custom Integrated Circuits Conference (CICC), Newport Beach, CA, USA, 2022, pp. 1-2, doi: 10.1109/CICC53496.2022.9772813.

[IEEE Link](https://ieeexplore.ieee.org/document/9159692) \

## Keypoints

- dual-path SSPLL with FBPNC
  - main path with LPF
  - extra path with HPF
    introduce new in-band zero and pole
    - ​extend BW
    - compensate PM
- new in-band zero/pole pair
  improve loop gain at lower freq

## Background

- RO has poor phase noise
- PN cancellation techniques
  - feedforward phase noise cancellation (FFPNC)
  - feedback phase noise cancellation (FBPNC)
  - based on VCDL: power, area++

<img src="https://api2.mubu.com/v3/document_image/00983291-3bf0-470a-8c2d-3cd20df00ca6-216525.jpg" width = "500" alt="Proposed Dual-Path SSPLL" align=center />

## Conclusion

- **TECH** 28 nm \
- **REF** 20 MHz \
- **OUT** 2GHz \
- **REF SPUR** NA \
- **POWER** 2.96 mW @ 0.8 V \
- **RMS JITTER** 2.63 fs (1KHz ~100M Hz) \
- **FOM** -226.91 dB \

## Important Reference

> *feedforward phase noise cancellation (FFPNC) techniques \[1\]–\[4\]*
>
> - \[1\] S. Min et al., “A 90-nm CMOS 5-GHz Ring-Oscillator PLL with Delay-Discriminator-Based Active Phase-noise Cancellation,” JSSC, May 2013.
>
> - \[2\] A. Li et al., “A Spur-and-Phase-Noise-Filtering Technique for Inductor-Less Fractional-N Injection-Locked PLLs,” JSSC, Aug. 2017.
>
> - \[3\] Z. Huang et al., “A 4.2 μs-settling time 3rd-order 2.1 GHz phase-noise rejection PLL using a cascaded time-amplified clock-skew sub-sampling DLL,” ISSCC, Jan. 2016.
>
> - \[4\] S. S. Nagam et al., “A Low-Jitter Ring-Oscillator Phase-Locked Loop Using Feedforward Noise Cancellation with a Sub-Sampling Phase Detector,” JSSC, Mar. 2018.
>
> *feedback phase noise cancellation (FBPNC) technique*
>
> - \[5\] H. Ting et al., “A 5.25GHz Subsampling PLL with a VCO-Phase- Noise Suppression Technique,” ISSCC, Feb. 2020.
