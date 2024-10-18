---
title: >-
  ISSCC-2024 19.1 A 7.5GHz Subharmonic Injection-Locked Clock Multiplier with a
  62.5MHz Reference, -259.7dB FoMJ, and -56.6dBc Reference Spur
toc: true
tags:
  - ISSCC
  - 2024
  - ILCM
  - LC
  - KAIST
abbrlink: 12490
date: 2024-10-18 20:22:39
---

![Keypoints](https://s21.ax1x.com/2024/10/18/pAU2aG9.png) \

##### Full Citation

H. Choi and S. Cho, "**19.1 A 7.5GHz Subharmonic Injection-Locked Clock Multiplier with a 62.5MHz Reference, -259.7dB FoMJ, and -56.6dBc Reference Spur**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 348-350, doi: 10.1109/ISSCC49657.2024.10454375.

[IEEE Link](https://ieeexplore.ieee.org/document/10454375) \

## Keypoints

- SILCM with strong injection and low spur
- injection schemes with reset and recovery
- reset : short outputs
- recovery
  - repair output waveform
  - levels
  - timing
- implementation
  - injection signal generation
  - injection circuit
  - interval generator
    - cross high, mid, low threshold
    - period : period of mid 
    - amplitude : period from high to low
  - div-by-4 output : the injection at the end of the 4 cycles
  - calibration loops
    - VCO frequency
    - recovery levels : adjust resistor
    - recovery timing : recovery pulse CH_P to CH_N
    - comparator offset

## Background

- subharmonic injection locking (SIL)
  - injection strength tradeoff of phase noise reduction and ref spur
  - for RO
    - square-wave-like waveform
    - strong injection with calibration is possible
  - for LC
    - sinusoidal nature
    - injection through shorted output \
      reset the tank charge
    - sever tradeoff  and less benefit from calibration

<img src="https://s21.ax1x.com/2024/10/18/pAU2wx1.png" width = "500" alt="Overall architecture" align=center />

<img src="https://s21.ax1x.com/2024/10/18/pAU2BKx.png" width = "500" alt="Detailed circuitry" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  62.5 MHz \
**OUT**  6.75 ~ 7.5 GHz \
**REF SPUR**  -56.6 dBc \
**POWER**  2.33 mW  \
**RMS JITTER**  92.3 fs \
**FOM**  -257 dB \

## Important References

> *phase-noise reduction depends on the injection strength* \
> [1] N. Da Dalt, “An Analysis of Phase Noise in Realigned VCOs,” IEEE TCAS-II, vol. 61, no. 3, pp. 143–147, Mar. 2014.
> 
> *LC ILCM with shorted output*
> [2] Y.-C. Huang et al., “A 2.4GHz Sub-Harmonically Injection-Locked PLL with Self-Calibrated Injection Timing,” ISSCC, pp. 338-339, Feb. 2012. \
> [3] I.-T. Lee et al., “A Divider-Less Sub-Harmonically Injection-Locked PLL with Self-Adjusted Injection Timing,” ISSCC, pp. 414-415, Feb. 2013.
> 
> *calibrated but poor ref spur* \
> [4] D.-E. Jhou et al., “A 5.12-GHz Fractional-N Frequency Synthesizer with an LC-VCO-based MDLL,” IEEE Symp. VLSI Circuits, pp. C132-C133, June 2017.
> 
> *high Fref* \
> [5] H. Zhang et al., “0.2mW 70fsrms-Jitter Injection-Locked PLL Using De-Sensitized SSPD-Based Injecting-Time Self-Alignment Achieving -270dB FoM and -66dBc Reference Spur,” IEEE Symp. VLSI Circuits, pp. C38-C39, June 2019. \
> [7] Y.-A. Li et al., “A 138fsrms-Integrated-Jitter and -249dB-FoM Clock Multiplier with -51dBc Spur Using a Digital Spur Calibration Technique in 28-nm CMOS,” IEEE Symp. VLSI Circuits, pp. C42-C43, June 2019.
> 
> *pulse-width comparator (PWC)* \
> [6] H. Kim et al., “A 2.4GHz 1.5mW Digital MDLL Using Pulse-Width Comparator and Double Injection Technique in 28nm CMOS,”ISSCC, pp. 328-329, Feb. 2016.