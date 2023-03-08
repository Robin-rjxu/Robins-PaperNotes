---
title: >-
  ASSCC-2021 A 3.7-to-4.1GHz Narrowband Digital Bang-Bang PLL with a Multitaps
  LMS Algorithm to Automatically Control the Bandwidth Achieving 183fs
  Integrated Jitter
toc: true
tags:
  - ASSCC
  - 2021
  - Polimi
  - PLL
abbrlink: 11131
date: 2023-03-09 00:51:58
---

![Keypoints](https://api2.mubu.com/v3/document_image/66bcd39d-9252-4b6b-884c-a27df6efe189-216525.jpg) \

##### Full Citation

M. Mercandelli, L. Bertulessi, C. Samori and S. Levantino, "**A 3.7-to-4.1GHz Narrowband Digital Bang-Bang PLL with a Multitaps LMS Algorithm to Automatically Control the Bandwidth Achieving 183fs Integrated Jitter**," 2021 IEEE Asian Solid-State Circuits Conference (A-SSCC), Busan, Korea, Republic of, 2021, pp. 1-3, doi: 10.1109/A-SSCC53895.2021.9634706.

[IEEE Link](https://ieeexplore.ieee.org/document/9634706) \

## Keypoints

- multi-tap finite-impulse response (FIR) adaptive filter
  - accurately replicate in the digital domain the PLL loop filter
  - extract the equivalent gain of the VCO-divider-BPD chain
    g = N KT Kbpd
  - loop-gain normalization
- FIR coefficients estimation
  - replicate the oscillator via an digital integrator
    from q[k] the integrated training sequence, s[k]
  - digitally-tunable FIR filtere stimating the analog LPF TF
- adaptive filter algorithm : 16 taps
  mimic the DLF output {input},  goes through PLL and get PD output e[k] {input}
  - input : s[k], integrated QE q[k] of the DSM for DCO
  - filter result :  the FIR TF g
  - output : q[k] x g
  - error : p[k], PLL output e[k] subtract FIR output q[k] x g
  - tap number is sized
    - slowest filter time constant
    - the reference period

## Background

- BB DPLL
  - achieving state-of-the-art phase noise, jitter
  - fast-lock performances
  - bandwidth
    - is subject to PVT variations
    - depends on the system phase noise level
- previously presented ABWC systems
  - the PLL requires a narrow bandwidth
    - aggressive out-of-band filtering 
    - to meet the spectral phase noise mask
- a narrow-band loop filter in BB DPLL
  - would significantly alter the transfer function
    from q[k] (used as LMS training sequence) to the BPD output, e[k]
  - impairing the DPLL bandwidth regulation

<img src="https://api2.mubu.com/v3/document_image/7f6ca736-25ca-40ad-9c28-6a3b62fc5af1-216525.jpg" width = "600" alt="DPLL and multitaps ABWC algorithm linearized model" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  52 MHz \
**OUT**  3.7 - 4.1 GHz \
**POWER**  5.3 mW  \
**RMS JITTER**  183 fs \
**FOM**  -247.5 dB \

## Important References

> *BB DPLL with low PN and fast locking* \
> [1] A. Santiccioli et al., "A 66-fs-rms Jitter 12.8-to-15.2-GHz Fractional-N Bang–Bang PLL with Digital Frequency-Error Recovery for Fast Locking," in IEEE Journal of Solid-State Circuits, vol. 55, no. 12, pp. 3349-3361, Dec. 2020. \
> [2] L. Bertulessi, et al., "A low-phase-noise digital bang-bang PLL with fast lock over a wide lock range," 2018 IEEE International Solid- State Circuits Conference - (ISSCC), 2018, pp. 252-254.
> 
> *automatic bandwidth control (ABWC)* \
> [4] M. Mercandelli et al., "A Background Calibration Technique to Control the Bandwidth of Digital PLLs," in IEEE Journal of Solid-State Circuits, vol. 53, no. 11, pp. 3243-3255, Nov. 2018. \
> [5] C. Tsai et al., "Analysis of a 28-nm CMOS Fast-Lock Bang-Bang Digital PLL with 220-fs RMS Jitter for Millimeter-Wave Communication," in IEEE Journal of Solid-State Circuits, vol. 55, no. 7, pp. 1854-1863, July 2020. \
> [6] M. Youssef, et al., "A Low-Power GSM/EDGE/WCDMA Polar Transmitter in 65-nm CMOS," in IEEE Journal of Solid-State Circuits, vol. 46, no. 12, pp. 3061-3074, Dec. 2011
