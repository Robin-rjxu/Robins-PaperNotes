---
title: >-
  CICC-2023 A 2.6GHz ΔΣ Fractional-N Bang-Bang PLL with FIR-Embedded
  Injection-Locking Phase-Domain Low-Pass Filter
toc: true
tags:
  - CICC
  - 2023
  - PLL
  - BBPD
  - FIR
  - THU
abbrlink: 23542
date: 2024-01-11 23:57:12
---

![Keypoints](https://i0.imgs.ovh/2024/01/11/IjJTD.png) \

##### Full Citation

L. Feng, W. Rhee and Z. Wang, "**A 2.6GHz ΔΣ Fractional-N Bang-Bang PLL with FIR-Embedded Injection-Locking Phase-Domain Low-Pass Filter**," 2023 IEEE Custom Integrated Circuits Conference (CICC), San Antonio, TX, USA, 2023, pp. 1-2, doi: 10.1109/CICC57935.2023.10121264.

[IEEE Link](https://ieeexplore.ieee.org/document/10121264)\

## Keypoints

- DTC-free frac IL-FIR BB-PLL
  - FIR-embedded phase-domain LPF (PDLPF)
  - attenuate QN and suppress noise aliasing
  - require no NL calibration
  - not sensitive to mismatch/NL/supply
- implementation
  - FIR-IL in the fb path
    - ILO 
    - 1st-order PLL
    - anti-aliasing PDLPF
    - reduce area, power and complexity
  - 8-tap FIR in phase domain
    - average QN before injected to ILO
    - ensure ILO locking
- fractional operation
  - DCO --> 4/5 prescaler
  - DSM modulate FCW at high-freq
  - 8-tap FIR phase filter
    - 8-phase phase rotator (7 DFFs)
    - pulse generator
      - adjustable width and amplitude
      - inj strength and BW
    - pulse-gm-current is summed up
  - ILO filters QN as PDLPF
    - locked at 600MHz 
    - BPF BW ~ 5M, Q ~ 60

## Background

- BB-DPLL enables good frequency generation
  - low complexity
  - capacity of modulation
  - good in-band PN
  - but requires DTC compensate QN
    - require high resolution
    - complex calibration for non-lineariy
    - vulnerable to supply distrubance
- DTC-free frac BB-PLL
  - FIR-embedded 

<img src="https://i0.imgs.ovh/2024/01/12/Ij5rs.png" width = "700" alt="Proposed BBPLL with FIR-IL PDLPF" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  60 MHz \
**OUT**  2.2~2.7 GHz \
**REF SPUR**  -78.7 dBc \
**FRAC SPUR**  -59 dBc \
**POWER** 4.3 mW  \
**RMS JITTER**  1.32 ps \
**FOM**  -231 dB \

## Important References

> *BBPD-PLL* \
> [1] S. M. Dartizio et al., "A 68.6fsrms-Total-Integrated-Jitter and 1.56μs-Locking-Time Fractional-N Bang-Bang PLL Based on TypeII Gear Shifting and Adaptive Frequency Switching", ISSCC, pp. 386387, Feb. 2022.
> 
> *DTC compensation* \
> [2] H. Park et al., "A 365fsrms-Jitter and -63 dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/Third-Order Nonlinearity Cancelation and a ProbabilityDensity-Shaping ΔΣM", ISSCC, pp. 442-443, Feb. 2021.
> 
> *anti-aliasing PDLPF* \
> [3] L. Feng et al., "A Quantization Noise Reduction Method for DeltaSigma Fractional-N PLLs Using Cascaded Injection-Locked Oscillators", IEEE TCAS-II, vol. 69, no. 5, pp. 2448-2452, May 2022.
> 
> *PLL-based PDLPF* \
> [4] P. Park et al., "A 2.4GHz Fractional-N Frequency Synthesizer with High-OSR ΔΣ Modulator and Nested PLL", IEEE JSSC, vol. 47, no. 10, pp. 2433-2443, Oct. 2012. \
> [5] M. Osada et al., "An Inductorless Fractional-N PLL Using Harmonic-Mixer-Based Dual Feedback and High-OSR Delta-SigmaModulator with Phase-Domain Filtering", ESSCIRC, pp. 245-248, Sept. 2022.
> 
> *FIR noise filtering without NL cali* \
> [6 ]X. Yu et al., "AΔΣ Fractional-N Frequency Synthesizer with Customized Noise Shaping for WCDMA/HSDPA Applications", IEEE JSSC, vol. 44, no. 8, pp. 2193-2201, Aug. 2009.
