---
title: >-
  ESSERC-2024 A 48-58GHz Frac-N DPLL achieving 137fs integrated jitter and fast
  locking time below 1μs
toc: true
tags:
  - ESSERC
  - 2024
  - DPLL
  - DPD
  - Infineon
abbrlink: 49916
date: 2024-12-06 07:55:02
---

![Keypoints](https://s21.ax1x.com/2024/12/07/pA7mckV.png) \

##### Full Citation

L. Grimaldi et al., "**A 48-58GHz Frac-N DPLL achieving 137fs integrated jitter and fast locking time below 1μs**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 689-692, doi: 10.1109/ESSERC62670.2024.10719534.

[IEEE Link](https://ieeexplore.ieee.org/document/10719534) \

## Keypoints

- Digital Hop Control (DHC)
  - digital pre-distortion
  - compensate oscillator’s non-linearity
  - two-point modulation
    - frequency control word (FCW) to MMD
    - to the output of the DLF
    - scaling factor Kf
      - DCO frequency linear gain
      - match the low-pass and the high-pass path
      - pre-distorted by means of a LUT based DPD
        - predistort the hopping control word
        - compensate the residual frequency error
        - three frequency points are measured
- clock domain crossing (CDC)
  - between slow and fast logic
  - principle
    - slow control signals is synchronized to the fast domain
    - generate a pulse with a programmable shift register
    - reset the accumulator
    - overflow of the counter for the data handover
  - circuits
    - edge detection logic
    - synchronization control
    - shift register
    - accumulator
- 47.9-57.6 GHz fractional-N DPLL
  - features
    - oversampled digital control scheme driving the DCO
    - digital pre-distortion for fast freq. hopping
  - 26-GHz DCO
  - push-push 2x freq. multiplier
  - digital-to-time converter (DTC)
    - cancels QN
    - gain calibration
    - on the reference clock path
    - followed by a narrow-range multi-bit TDC
  - DIV
    - CML-based divide-by-2 divider
    - feedback multi-modulus-divider (MMD)
    - 2nd-order DSM 
  - digital loop filter (DLF)
    - two infinite impulse response (IIR) filters
    - output is summed to the DHC
  - 2nd-order DSM dithering the DCO
    - oversampling
      - fast clock from integer-N MDLL
      - part of the SoC
      - share the same reference
      - clock domain crossing block (CDC)
    - pushes the DSM QN towards higher freq.
    - reduce impact on the PN
  - DCO
    - lass-B topology
    - tail inductor

## Background

- high-performance mm-wave wireless transceivers
  - high data rate
  - more complex modulation schemes
  - frequency synthesizers
    - low-jitter
    - high-spectral-purity
    - fast-locking 
- fast frequency hopping
  - digital PLL (DPLL)
  - reference clock
    - high-frequency 
    - ultra-low-phase-noise
    - expensive and high system cost
    - standard and low-cost XO but high power

<img src="https://s21.ax1x.com/2024/12/07/pA7myT0.png" width = "500" alt="Architecture of the proposed 50GHz Frac-N DPLL" align=center />

<img src="https://s21.ax1x.com/2024/12/07/pA7mswq.png" width = "500" alt="Clock Domain Crossing (CDC) design and the fast clock logic and Digital Hop Control (DHC) scheme" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  100 MHz \
**OUT**  47.9 ~ 57.6 GHz \
**REF SPUR**  -50 dBc \
**FRAC SPUR**  -50.5 dBc \
**POWER**  30 mW  \
**RMS JITTER**  137 fs \
**FOM**  -242 dB \

## Important References

> *fast hopping DPLL* \
> [1] A. Hussein, S. Vasadi, M. Soliman and J. Paramesh, ”19.3 A 50-to-66GHz 65nm CMOS all-digital fractional-N PLL with 220fsrms jitter,” 2017 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2017, pp. 326-327. \
> [2] L. Grimaldi et al., ”16.7 A 30GHz Digital Sub-Sampling Fractional-N PLL with 198fsrms Jitter in 65nm LP CMOS,” 2019 IEEE International Solid-State Circuits Conference - (ISSCC), San Francisco, CA, USA, 2019, pp. 268-270.
> 
> *ultra-low-phase-noise and high-frequency reference clock* \
> [3] Y. Zhao, O. Memioglu, L. Kong and B. Razavi, ”A 56-GHz Fractional-N PLL With 110-fs Jitter,” in IEEE Journal of Solid-State Circuits, vol. 58, no. 1, pp. 57-67, Jan. 2023.
> 
> *narrow-range multi-bit TDC* \
> [4] R. Nonis, W. Grollitsch, T. Santa, D. Cherniak and N. D. Dalt, ”A 2.4psrms-jitter digital PLL with Multi-Output Bang-Bang Phase Detector and phase-interpolator-based fractional-N divider,” 2013 IEEE International Solid-State Circuits Conference Digest of Technical Papers, San Francisco, CA, USA, 2013, pp. 356-357.
> 
> *DTC gain calibration* \
> [5] D. Tasca, M. Zanuso, G. Marzin, S. Levantino, C. Samori and A. L. Lacaita, ”A 2.9–4.0-GHz Fractional-N Digital PLL With Bang-Bang Phase Detector and 560- fsrms Integrated Jitter at 4.5-mW Power,” in IEEE Journal of Solid-State Circuits, vol. 46, no. 12, pp. 2745-2758, Dec. 2011.
> 
> *DPD for the DCO gain* \
> [6] S. M. Dartizio et al., ”A 68.6fsrms-total-integrated-jitter and 1.56µs-locking-time fractional-N bang-bang PLL based on type-II gear shifting and adaptive frequency switching,” 2022 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 1-3.
> 
> *frequency hopping* \
> [7] L. Bertulessi, L. Grimaldi, D. Cherniak, C. Samori and S. Levantino, ”A low-phase-noise digital bang-bang PLL with fast lock over a wide lock range,” 2018 IEEE International Solid-State Circuits Conference - (ISSCC), San Francisco, CA, USA, 2018, pp. 252-254. \
> [8] C. -H. Tsai, F. Pepe, G. Mangraviti, Z. Zong, J. Craninckx and P. Wambacq, ”A 22.5–27.7-GHz Fast-Lock Bang-Bang Digital PLL in 28-nm CMOS for Millimeter-Wave Communication With 220-fs RMS Jitter,” ESSCIRC 2019 - IEEE 45th European Solid State Circuits Conference (ESSCIRC), Cracow, Poland, 2019, pp. 111-114. \
> [9] A. Santiccioli et al., ”A 66-fs-rms Jitter 12.8-to-15.2-GHz Fractional-N Bang–Bang PLL With Digital Frequency-Error Recovery for Fast Locking,” in IEEE Journal of Solid-State Circuits, vol. 55, no. 12, pp. 3349-3361, Dec. 2020. \
> [10] W. Wu, X. Bai, R. B. Staszewski and J. R. Long, ”A 56.4-to-63.4GHz spurious-free all-digital fractional-N PLL in 65nm CMOS,” 2013 IEEE International Solid-State Circuits Conference Digest of Technical Papers, San Francisco, CA, USA, 2013, pp. 352-353. \
> [11] Z. Zong, P. Chen and R. B. Staszewski, ”A Low-Noise Fractional- N Digital Frequency Synthesizer With Implicit Frequency Tripling for mm-Wave Applications,” in IEEE Journal of Solid-State Circuits, vol. 54, no. 3, pp. 755-767, March 2019