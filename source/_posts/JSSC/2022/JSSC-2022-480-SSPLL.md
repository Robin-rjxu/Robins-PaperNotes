---
title: JSSC-2022 A 480-Multiplication-Factor 13.2-to-17.3GHz Sub-Sampling PLL
  Achieving 6.6mW Power and -248.1 dB FoM Using a Proportionally Divided Charge
  Pump
toc: true
tags:
  - JSSC
  - 2022
  - PLL
  - Berkeley
abbrlink: 2661
date: 2023-02-05 19:04:10
---

![keypoints](https://api2.mubu.com/v3/document_image/6ae868ce-aff2-4afd-8ebf-559356f56834-216525.jpg) \

##### Full Citation
L. Zhang and A. Niknejad, "**A 480-Multiplication-Factor 13.2-to-17.3GHz Sub-Sampling PLL Achieving 6.6mW Power and -248.1 dB FoM Using a Proportionally Divided Charge Pump**," 2022 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 1-3, doi: 10.1109/ISSCC42614.2022.9731760.

[IEEE Link](https://ieeexplore.ieee.org/document/9731760) \

## Keypoints

- Sub-sampling PLL
  - combine SS loop and DIV-CP loop by adding another RC leg
  - the SS loop and the FLL share the same poles but distinct zeros
  - does not incur any power or area penalty (loop caps maintain the same)
  - the current ratio is realized by splitting mirrored current

## Background

- requirement for direct high M-factor frequency synthesis with low PN and low power consumption
- SS-PLLs prone to false frequency acquisition when M is high
- LGR (SS loop:FLL) must be close to unity to ensure the stability
  - large I_CP in the FLL

<img src="https://api2.mubu.com/v3/document_image/b2513615-9f37-4510-b521-4abcfb7a4bfd-216525.jpg" width = "500" alt="Proposed SSPLL with the frequency lock loop (FLL)" align=center />

## Conclusion

- **TECH**  28nm \
- **REF**  30/60MHz \
- **OUT**  13.2~17.3 GHz \
- **REF SPUR**  -62.3/-57.2 dBc \
- **FRAC SPUR**  NA \
- **POWER**  6.6 mW \
- **RMS JITTER**  153.4/116.5 fs \
- **FOM**  -248.1/-250.5 dB \

## Important Reference

> *duty-cycled FLL*
> 
> [1] H. Liu et al., “16.1 A 265μW fractional-N digital PLL with seamless automatic switching subsampling/sampling feedback path and duty-cycled frequency-locked loop in 65nm CMOS,” ISSCC, pp. 256-258, Feb. 2019. \
> 
> *diturbance FLL*
> 
> [2] Y. Lim et al., “17.8 A 170MHz-lock-in-range and −253dB-FoMjitter 12-to-14.5GHz subsampling PLL with a 150μW frequency-disturbance-correcting Loop using a low-power unevenly spaced edge generator,” ISSCC, pp. 280-282, Feb. 2020. \

