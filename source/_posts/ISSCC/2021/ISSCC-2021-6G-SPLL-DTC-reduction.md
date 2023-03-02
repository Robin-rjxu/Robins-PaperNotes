---
title: >-
  ISSCC-2021 32.2 A 14nm Analog Sampling Fractional-N PLL with a Digital-to-Time
  Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs
  at Near-Integer Channels
toc: true
tags:
  - ISSCC
  - 2021
  - Samsung
  - PLL
abbrlink: 14141
date: 2023-03-02 23:18:10
---

![Keypoints](https://api2.mubu.com/v3/document_image/02064a0b-2847-49ad-8ed2-1c860e223f09-216525.jpg) \

##### Full Citation

W. Wu et al., "**32.2 A 14nm Analog Sampling Fractional-N PLL with a Digital-to-Time Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs at Near-Integer Channels**," 2021 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2021, pp. 444-446, doi: 10.1109/ISSCC42613.2021.9365850.

[IEEE Link](https://ieeexplore.ieee.org/document/9365850) \

## Keypoints

- 6GHz fractional-N sampling PLL
  - DTC range-reduction technique
  - modified multi-modulus divider (MMD) and the DSM
     mux at the MMD output to select clock, CKFB1, and a delayed-by-Tvco/2, CKFB2
  - sampling phase detector (SPD)
    - the rising edge of CKDTC triggers a well-defined voltage ramp
    - feedback CKFB samples the voltage as prop Vctrl directly
    - gm + C as the intg path
- LMS loops for
  - DCO duty cycle error
  - DTC gain
  - reference duty cycle error
  - sign-sign LMS enabled by Vref dithering CMP
- circuits
  - clock doubler of the CKREF further reduces the in-band PN
  - dual-core VCO : noise filtering ind inside the main ind
  - PTAT voltage compensate VCO freq drift

## Background

- DTC is used to cancel fractional quantization error
  - fine resolution
  - large range
    (400ps for a 5GHz VCO and mash1-1 DSM)
  - contribute to in-band noise
  - NL increases spurs and noise folding
  - Reducing the DTC ==> relax PN, linearity, and design complexity

<img src="https://api2.mubu.com/v3/document_image/19a9cccd-4e7a-40db-9e47-59dc36071d00-216525.jpg" width = "500" alt="Block diagram of the presented fractional-N sampling PLL" align=center />

## Conclusion

**TECH**  14 nm \
**REF**  76.8 MHz \
**OUT**  5-7 GHz \
**REF SPUR**  -72 dBc \
**FRAC SPUR**  -72.4 dBc \
**POWER**  14.2 mW \
**RMS JITTER**  80 fs \
**FOM**  -250.4 dB \

## Important References

> *DTC in frac-N sampling PLL* \
> [1] W. Wu et al., “A 28-nm 75-fsrms Analog Fractional-N Sampling PLL with a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction”, IEEE JSSC, vol. 54, no. 5, pp. 1254-1265, May 2019. \
> [2] M. Mercandelli et al., “A 12.5GHz Fractional-N Type-I Sampling PLL Achieving 58fs Integrated Jitter”, ISSCC, pp. 274-276, Feb. 2020.
> 
> *reducing DTC range* \
> [3] L. Grimaldi et al., “A 30GHz Digital Sub-Sampling Fractional-N PLL with 198fsrms Jitter in 65nm LP CMOS”, ISSCC, pp. 268-270, Feb. 2019. \
> trade-of of range and noise
> [4] N. Markulic et al., “A 10-bit 550-fs Step Digital-to-Time Converter in 28nm CMOS”, ESSCIRC, pp. 79-82, 2014.
> 
> *coupled-VCO* \
> [5] D. Murphy et al., “A 27-GHz Quad-Core CMOS Oscillator With No Mode Ambiguity”, IEEE JSSC, vol. 53, no. 11, pp. 3208-3216, Nov. 2018.
