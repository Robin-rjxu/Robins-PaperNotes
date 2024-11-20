---
title: >-
  CICC-2024 A 6.8-to-14.4GHz Octave-Tuning Fractional-N Charge-Pump PLL with
  Slide-Dithering-Based Background DTC Nonlinearity Calibration for Near-Integer
  Fractional Spur Mitigation Achieving 78fs RMS Jitter and -258.6dB FoMT
toc: true
tags:
  - CICC
  - 2024
  - CP
  - PLL
  - DTC
  - TA
  - VCO
  - dithering
  - UESTC
abbrlink: 4688
date: 2024-11-20 15:09:56
---

![Keypoints](https://s21.ax1x.com/2024/11/20/pAWUNy4.png) \

##### Full Citation

Z. Ye, X. Geng, Z. Shi, H. Zhang, Q. Xie and Z. Wang, "**A 6.8-to-14.4GHz Octave-Tuning Fractional-N Charge-Pump PLL with Slide-Dithering-Based Background DTC Nonlinearity Calibration for Near-Integer Fractional Spur Mitigation Achieving 78fs RMS Jitter and -258.6dB FoMT**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529020.

[IEEE Link](https://ieeexplore.ieee.org/document/10529020) \

## Keypoints

- slide-dithering-based NLF extraction technique
  - perform background DTC calibration
  - introduce randomization of CW
    - NLF is spread to higher frequencies
    - less filtered by the HP TF
    - make the important fingerprint detectable
    - mitigate the fractional spurl like TIPM \
      Time-Invariant-Probability Modulator
  - CW limiter
    - determine whether to randomize the CW
    - high select-0 probability
      - increase the probability of CW=0 for both DTCs to 0.25
      - effectively extract the quasi-static offset
      - calibrate the offset
- hybrid gear estimation and compensation (GEC) algorithm
  - accelerate the DTC calibration
  - two-step
    - fast-converge LMS to set the coarse value of the GEC LUT
    - background cali. to estimate precise DTC delay
- 6.8-14.4GHz fractional-N PLL in 65nm CMOS
  - fractional QE compensation
    - Two Main DTCs
    - an Aux DTC
  - DTC calibration
    - FCW subtractive dithering with 1st-order DSM
    - GEC to compensate the nonlinearity of both Main DTCs
    - LMS-based cali. for CW generation of Aux DTC
  - PD
    - CP
    - TAPFD
    - BBPD 
      - compensate DTC
      - compensate BBPD static phase error
  - triple mode VCO

## Background

- wireless communication systems
  - fractional-N phase-locked loop (PLL)
  - better rms jitter : sub-100fs
  - lower spurious tones 
    - discrete jitter is becoming dominant
  - higher figure-of-merit (FoM)
- Digital-to-time converter (DTC)
  - cancel the quantization error (QE)
  - linearity of the DTC is of vital importance
  - trade-off : linearity <--> thermal noise
- difficult to extract DTC’s nonlinearity fingerprint (NLF)
  - error extraction
    - HP TF from DTC output to the PFD output
    - low-frequency spectrum of NLF is deeply filtered
  - quasi-static offset additive delay in the DTC
    - hard to extracted due to HP TF
    - accumulated in the background calibration
    - translate to low-frequency noise and spurs

<img src="https://s21.ax1x.com/2024/11/20/pAWUYSU.png" width = "500" alt="Block diagram of the dual-DTC-assisted TA-CPPLL" align=center />

<img src="https://s21.ax1x.com/2024/11/20/pAWUtlF.png" width = "500" alt="Issues of background DTC nonlinearity calibration  and proposed solution" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  100 MHz \
**OUT** 6.8 ~ 14.4 GHz \
**REF SPUR**  -73.4 dBc \
**FRAC SPUR**  -63.3 dBc \
**POWER**  16.18 mW  \
**RMS JITTER**  77.96 fs \
**FOM**  -250.1 dB \

## Important References

> *DTC cancels QE* \
> [1] N. Markulic et al., "A DTC-Based Subsampling PLL Capable of Self-Calibrated Fractional Synthesis and Two-Point Modulation,” in IEEE JSSC, Dec, 2016.
> 
> *dealt with fractional spur at MHz* \
> [2] X. Geng, et al., "A 26GHz Fractional-N Charge-Pump PLL Based on A Dual- DTC-Assisted Time-Amplifying-Phase-Frequency Detector Achieving 37.1fs and 45.6fs rms Jitter for Integer-N and Fractional-N Channels," IEEE CICC, Apr. 2023.
> 
> *TIPM technique* \
> [3] T. Seong, et al., "A -58dBc-Worst-Fractional-Spur and -234dB-FoM 5.5GHz Ring-DCO-Based Fractional-N DPLL Using a Time-Invariant-Probability Modulator Generating a Nonlinearity-Robust DTC-Control Word", IEEE ISSCC, Feb. 2020.
> 
> *1st-order DSM with FCW subtractive dithering* \
> [4] S. Dartizio, et al., " A 76.7fs-lntegrated-Jitter and -71.9dBc In-Band Fractional- Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering," IEEE ISSCC, Feb. 2023.