---
title: >-
  ISSCC-2024 10.4 A 45.5fs-Integrated-Random-Jitter and -75dBc-Integer-Boundary-Spur BiCMOS Fractional-N PLL with Suppression of Fractional, Horn, and Wandering Spurs
toc: true
abbrlink: 34771
date: 2024-10-12 21:40:31
tags:
  - ISSCC
  - 2024
  - PLL
  - CP
  - DSM
  - UCD
---

![Keypoints](https://s21.ax1x.com/2024/10/12/pAY5861.png) \

##### Full Citation

M. P. Kennedy, V. Mazzaro, S. Tulisi, M. Scully, N. McDermott and J. Breslin, "**10.4 A 45.5fs-Integrated-Random-Jitter and -75dBc-Integer-Boundary-Spur BiCMOS Fractional-N PLL with Suppression of Fractional, Horn, and Wandering Spurs**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 194-196, doi: 10.1109/ISSCC49657.2024.10454462.

[IEEE Link](https://ieeexplore.ieee.org/document/10454462) \

## Keypoints

- enhanced non-linearity-induced-noise-performance (ENOP) D-DSM
  - provably immune to polynomial distortion
  - no horn or wandering spurs
- frac-N CP PLL
  - ENOP D-DSM (mixed radix MASH-ENOP hybrid) 
    - main and auxiliary modulators (24b+25b) \
      49b frequency resolution
    - STF remains the same
    - NTF is changed to (1-z-1)2(1-z-2-z-4+z-6+z-7-z-9) \
      compared to (1-z-2)3 for the MASH
    - quantization noise is greater as (-6 ~ +7) \
      (-3 ~ +4 for the MASH)
    - non-linearity-induced folded noise is greater
    - exhibit high frequency bump
    - slightly minimum in-band noise floor and integrated jitter
  - bipolar bleed current in CP to linearize the TIMS
  - fourth-order off-chip loop filter

## Background

- fractional-N PLL spurs
  - causes
    - quantization noise
    - time-interval measurement (TIMS) non-linearity
      - PFD+CP
      - TDC+DTC
  - types
    - fixed spurs
    - moving or wandering spurs
  - implementation: digital delta-sigma modulator D-DSM
- solution
  - CP-PLL : offset the operation point using bleed current
  - ADPLL
    - dither strategies
    - successive requantizer (SR) instead of D-DSM
    - probability mass redistribution (PMR)
    - DTC controlling
      - range reduction
      - probability density shaping (PDS)
      - subtractive dither

<img src="https://s21.ax1x.com/2024/10/12/pAY53lR.png" width = "500" alt="Block diagram of fractional-N frequency synthesizer with the mixed-radix MASH/ENOP divider controller" align=center />

## Conclusion

**TECH**  0.18 um SiGe BiCMOS \
**REF**  198.76 MHz \
**OUT**  6.4~12.8 GHz \
**REF SPUR**  -118 dBc \
**FRAC SPUR**  -75 dBc \
**POWER**  2100 mW  \
**RMS JITTER**  46.4 fs \

## Important References

> *successive requantizer (SR)* \
> [1] E. Familier and I. Galton, “Second and Third-Order Successive Requantizers for Spurious Tone Reduction in Low-Noise Fractional-N PLLs,” IEEE CICC, pp.1–4, May 2017.
> 
> *probability mass redistribution (PMR)* \
> [2] M.P. Kennedy et al., “4.48GHz 180nm SiGe BiCMOS Exact Frequency Fractional-N Frequency Synthesizer with Spurious-Tone Suppression Yielding a -80dBc In-Band Fractional Spur,” ISSCC, pp. 272–273, Feb. 2019.
> 
> *sampling PD and a DTC* \
> [3] W. Wu et al., “A 14nm Analog Sampling Factional-N PLL with a Digital-to-Time Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs at Near-Integer Channels,” ISSCC, pp. 444–445, Feb. 2021.
> 
> *probability density shaping (PDS)* \
> [4] H. Park et al., “A 365fsrms-Jitter and -63dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/Third-Order Nonlinearity Cancelation and a Probability-Density-Shaping ΔΣM,” ISSCC, pp. 442–443, Feb. 2021.
> 
> *DTC and subtractive dither* \
> [5] S.M. Dartizio et al., “A 76.7fs-Integrated-Jitter and -71.9dBc In-Band Fractional-Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slop DTC and FCW Subtractive Dithering,” ISSCC, pp. 78–79, Feb. 2023.
> 
> *enhanced non-linearity-induced-noise-performance (ENOP) DΔΣM* \
> [6] V. Mazzaro and M.P. Kennedy, “A Family of ΔΣ Modulators with High Spur Immunity and Low Folded Noise When Used in Fractional-N Frequency Synthesizers,” IEEE TCAS-I, vol. 69, no. 11, pp. 4499–4509, Nov. 2022.