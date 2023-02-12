---
title: ISSCC-2022 A Sub-100MHz Reference-Driven 25-to-28GHz Fractional-N PLL with −250dB FoM
toc: true
abbrlink: 28672
date: 2023-02-12 21:22:56
tags:
  - ISSCC
  - 2022
  - Broadcom
  - PLL
---

![Keypoints](https://api2.mubu.com/v3/document_image/ce41fdfa-791c-422c-a688-1880a1b41032-216525.jpg) \

##### Full Citation

D. Yang et al., "**A Sub-100MHz Reference-Driven 25-to-28GHz Fractional-N PLL with −250dB FoM**," 2022 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 384-386, doi: 10.1109/ISSCC42614.2022.9731628.

[IEEE Link](https://ieeexplore.ieee.org/document/9731628) \

## Keypoints

- 1st stage: sub-sampling int-N PLL
  - retimed div
  - SPD
    - constant and large gain
    - nulls ref spur
- 2nd stage: HM-PLL
  - unity fb gain
    not amplify DSM QE, PD and the 1st loop PN/spur
  - allow low-freq 1st stage
    high-Q
  - HM PD (sampler)
    - XOR gate + passive twin-T notch filter
    - simple RC and has wide BW
  - 7th harmonic
    - HM gain = 7 for the 1st stage
    - frac DIV lower DSM noise
- coupled VCO
  - halve ind allows large current
  - bowtie structure
  - only high-Q DM
    - cross lines for low-Q DC path
    - zero DC gain
  - 2 tail traces at twice freq resonance

## Background

- large closed loop gain of N in mm-wave freq synthesizer
- BW trade off
  - narrow BW  for input PN and spurs
  - wide BW for osc PN
- mm-wave osc is noisier
  - a capacitor bank  greatly compromises the quality factor (Q)
  - allocate more current to the VCO
  - raise to higher ref freq
- harmonic-mixing (HM)
  - suppress noise amplification
  - allow wide BW
- only one resonant mode for higher FoM

![The overall PLL architecture and the 2nd-stage HM PLL](https://api2.mubu.com/v3/document_image/7f1dc3a6-b219-4424-892d-4eba240d0bf0-216525.jpg) \

## Conclusion

**TECH**  7 nm \
**REF**  74 MHz \
**OUT**  25~28 GHz \
**REF SPUR**  -83 dBc \
**FRAC SPUR**  -61 dBc \
**POWER**  12.9 mW \
**RMS JITTER**  88 fs \
**FOM**  -250 dB \

## Important Reference

> *harmonic-mixing (HM) PLL to suppress noise amplification* \
> [4] D. Yang et al., “A Calibration-Free Triple-Loop Bang-Bang PLL Achieving 131fsrms Jitter and -70dBc Fractional Spurs,” ISSCC, pp. 266-268, Feb. 2019.
> [5] D. Yang et al., “An FBAR Driven −261dB FOM Fractional-N PLL,”IEEE RFIC, pp. 147-150, June 2021.
>
> *sub-sampling needs IL-div* \
> [2] L. Grimaldi et al., “A 30GHz Digital Sub-Sampling Fractional-N PLL with 198fsrms Jitter in 65nm LP CMOS,” ISSCC, pp. 268-270, Feb. 2019.
>
> *coupled VCO* \
> [6] D. Murphy and H. Darabi, “A 27-GHz Quad-Core CMOS Oscillator with No Mode Ambiguity,” IEEE JSSC, vol. 53, no. 11, pp. 3208-3216, Nov. 2018.
