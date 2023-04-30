---
title: ASSCC-2017 On-chip spur and phase noise cancellation techniques
toc: true
tags:
  - ASSCC
  - 2017
  - UCBerkeley
  - clock
abbrlink: 18545
date: 2023-04-26 23:05:47
---

![Keypoints](https://api2.mubu.com/v3/document_image/c4e46ad8-5b90-4158-a910-6dac5b98a3d0-216525.jpg) \

##### Full Citation

Y. -A. Li, M. Mar, B. Nikolić and A. M. Niknejad, "**On-chip spur and phase noise cancellation techniques**," 2017 IEEE Asian Solid-State Circuits Conference (A-SSCC), Seoul, Korea (South), 2017, pp. 109-112, doi: 10.1109/ASSCC.2017.8240228.

[IEEE Link](https://ieeexplore.ieee.org/document/8240228) \

## Keypoints

- notches again far-out spurs
  - idea
    - delay half of jitter period (1+exp(-sT))
    - interpolate it with the original clock
    - time-domain : average
    - freq-domain: offer notches at 1/2T, 3/2T, ...
  - limits
    - close-in notch requires large delay
      - notch bw shrinks
      - limit notch depth
    - improve by use (1-exp(-sT)
      - first notch is at dc
      - more flexible with delay line
- high-pass filtering on PN
  - extract PN and apply it back with opposite polarity
  - extract with a PD, down convert to basedband(differentiate)
  - integrate with CP+C
  - up-convert back with VCDL
  - non-idealies
    - mismatch : 10% is still effective
    - DC loop : loop with DLL structure
      - small DLL bw for effective cancellation
      - large bw PNC
      - => series capacitors
    - large tunable R to avoid leakage

## Background

- spur and phase noise are critical in communication system
  - TX side: worse LO that fails spectrum mask requirement
  - RX side: blocker induces reciprocal mixing with PN
- more power budget on clock sources
- post process module would be beneficial

<img src="https://api2.mubu.com/v3/document_image/17e7bbd9-5c60-428a-9785-8c53a6fedf4f-216525.jpg" width = "600" alt="Spurs and PN Cancellation" align=center />

## Conclusion

**TECH**  65 nm \
**FREQ**  1 GHz \
**PN_FREQ**  4M~200MHz \
**SPUR REDUCTION**  -15 dBc \
**PN REDUCTION**  -35 dBc \
**POWER**  11 mW  \

## Important References

> PN extract and cancellation \
> [1] F. Aflatouni et al., "Design methodology and architectures to reduce the semiconductor laser phase noise using electrical feed-forward schemes", IEEE TMTT, vol. 58, no. 11, 2010.
> 
> delay discriminator \
> [2] D. Scherer, The art of phase noise measurement, [online] Available: htlp://www.hparchive.com/seminar_notes/Scherer_Art_of_PN_measurement.pdf. \
> [3] A. Imani and H. Hashemi, "An FBAR/CMOS Frequency / Phase Discriminator and Phase Noise Reduction System", IEEE Trans. Microwave Theory & Tech., vol. 63, no. 5, pp. 1659-1665, May 2015. \
> [4] S. Min et al., "A 90nm CMOS 5GHz Ring Oscillator PLL with Delay-Discriminator Based Active Phase Noise Cancellation", IEEE RFIC, pp. 173-176, June 2012. \
> [5] S. Hao et al., "A 10 GHz delay line frequency discriminator and PD/CP based CMOS phase noise measurement circuit with −138.6 dBc/Hz sensitivity at 1 MHz offset", IEEE RFIC, pp. 63-66, 2015. \
> [6] S. Hao et al., "A 10 GHz Phase Noise Filter with 10.6 dB Phase Noise Suppression and −116 dBc/Hz Sensitivity at 1 MHz Offset", IEEE IMS, May 2016.

