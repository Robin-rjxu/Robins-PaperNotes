---
title: >-
  ISSC-2019 16.3 A −246dB Jitter-FoM 2.4GHz Calibration-Free Ring-Oscillator PLL
  Achieving 9% Jitter Variation Over PVT
toc: true
tags:
  - ISSCC
  - 2019
  - UMacau
  - PLL
  - SPD
  - RO
abbrlink: 58860
date: 2023-03-17 22:53:28
---

![Keypoints](https://api2.mubu.com/v3/document_image/699e9252-3086-440c-b79c-f46e2e3b7248-216525.jpg) \

##### Full Citation

X. Yang, C. -H. Chan, Y. Zhu and R. P. Martins, "**16.3 A −246dB Jitter-FoM 2.4GHz Calibration-Free Ring-Oscillator PLL Achieving 9% Jitter Variation Over PVT**," 2019 IEEE International Solid- State Circuits Conference - (ISSCC), San Francisco, CA, USA, 2019, pp. 260-262, doi: 10.1109/ISSCC.2019.8662312.

[IEEE Link](https://ieeexplore.ieee.org/document/8662312) \

## Keypoints

- RO PLL
  - naturally locked without FTL
  - stable type-II loop
  - PN cancellation effectively across PVT
    common PVT-tracking bias both in the sampler and the corrector
  - free-from ref-spur penalty
    discrete-time (DT) operations
- open-loop discrete-time PN cancellation
  - sample the noise information from the PLL output
  - cancel it by tuning a delay cell in time domain
- PN cancellator
  - constant delay cell
    RO edge at DT corrector later than the sampler
  - DC compensator
    reject DC information
  - common PVT-tracked bias
    provide bias for SPD1, SPD2 and DT corrector
  - DT corrector
    including bias PVT variation and sampled PN
- circuits
  - domino-based sampler
    reduce the reference spurs and maintain high speed
  - isolate VCO output and the sampler
  - SSPD1 for PLL and SSPD2 for DC compensator
  - copy current to the DT corrector

## Background

- low jitter PLL
  - LC oscillator : good PN but large area
    - ring -oscillator : poor PN but compact area
    - ILCM : good PN suppression, but dependent on inj accuracy
    - type-I and FPEC : large BW to suppress PN_osc but PVT sensitive

<img src="https://api2.mubu.com/v3/document_image/747a30b3-53fc-4269-a24d-faaccbe0dcfd-216525.jpg" width = "600" alt="Block diagram with the OPDTPNC concept" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  150 MHz \
**OUT**  2.08 - 2.72 GHz \
**REF SPUR**  -63 dBc \
**POWER**  4.1 mW  \
**RMS JITTER**  248 fs \
**FOM**  -246 dB \

## Important References

> *type-I PLL* \
> [3] L. Kong and B. Razavi, "A 2.4GHz 4mW Inductorless RF Synthesizer," IEEE JSSC, vol. 51, no. 3, pp. 626-635, Mar. 2016.
> 
> *FPEC with loop-gain calibration* \
> [4] Y. Lee et al., “A Low-Jitter and Low-Reference-Spur Ring-VCO Based Switched-Loop Filter PLL Using a Fast Phase-Error Correction Technique,” IEEE JSSC, vol. 53, no. 4, pp. 1192-1202, Apr. 2018.
> 
> *Sub-sampling PLL* \
> [6] X. Gao, et al., "A Low Noise Sub-Sampling PLL in Which Divider Noise is Eliminated and PD/CP Noise is Not Multiplied by N2," IEEE JSSC, vol. 44, no. 12, pp. 3253-3263, Dec. 2009.
