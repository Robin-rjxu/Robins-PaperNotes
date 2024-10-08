---
title: >-
  ISSCC-2024 7.8 A 69.3fs Ring-Based Sampling-PLL Achieving 6.8GHz-14GHz and
  −54.4dBc Spurs Under 50mV Supply Noise
toc: true
tags:
  - ISSCC
  - 2024
  - RO
  - PLL
  - SPD
  - UIUC
abbrlink: 36481
date: 2024-10-08 19:13:02
---

![Keypoints](https://s21.ax1x.com/2024/10/08/pAGc0HA.md.png) \

##### Full Citation

M. A. Khalil et al., "**7.8 A 69.3fs Ring-Based Sampling-PLL Achieving 6.8GHz-14GHz and −54.4dBc Spurs Under 50mV Supply Noise**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 138-140, doi: 10.1109/ISSCC49657.2024.10454445.

[IEEE Link](https://ieeexplore.ieee.org/document/10454445) \

## Keypoints

- proposed RO-PLL
  - sampling structure
  - high Kpd and wide BW
- type-III loop
  - expand frequency range
  - suppress supply noise and RO flicker
- circuits
  - sampling phase detector (SPD)
    - slope generator
    - TH circuit (Cs + Ch)
      - Rs = 60 Ohm
      - Cs = 1.2 pF
- high SPD gain and low KT/C noise
  - two integrators
    - GM1-C1 integrator
      - sets the integral path
      - make prop. and intg. share the same Vref1
    - GM2-C2 integrator + NMOS based regulator
      - set the RO supply voltage
  - type-III loop
    - wide continuous tuning range
    - expand the frequency tuning range
    - suppress supply noise and RO flicker PN
  - current mirror transconductance amplifiers
- a voltage-controlled RO (VCRO) tuning frequency by
  - 8-phase with 4 pseudu-differential AC-coupled buffers
  - supply voltage
  - varactor adjustments biased the gate via Rb
  - feed-forward resistors Rx
- integer-N divider
  - TSPC div-by-2

## Background

- multi-phase clock generation for high-speed serial link transceivers
  - minimal jitter < 100 fs
  - multiple sub-rate clock phases
- LC-based PLLs
  - large space
  - lack of efficiency in generation multiple phases
  - vulnerable to EM coupling
- RO-based
  - compact footprint
  - suitability multi-phase generation
  - excessive RO PN
  - supply requirement across a wide temperature range
- prior investigation : widen RO PN suppression BW
  - ILCM
  - extend the BW to 1/6 Fref
  - intricate FTL
- high Fref
- sampling PLLs

<img src="https://s21.ax1x.com/2024/10/08/pAGcwBd.png" width = "500" alt="Block diagram of the type-III supply-regulated sampling PLL." align=center />

## Conclusion

**TECH**  22 nm FinFET \
**REF**  812.5 MHz \
**OUT**  6.8~14 GHz \
**REF SPUR**  -62.2 dBc \
**POWER**  84.9 mW  \
**RMS JITTER**  69.3 fs \
**FOM**  -243.9 dB \

## Important References

> *LC-based PLL* \
> [1] W. Wu et al., “A 28-nm 75-fsrms Analog Fractional-N Sampling PLL With a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction,” IEEE JSSC, vol. 54, no. 5, pp. 1254-1265, May 2019.
> 
> *RO-based PLL* \
> [2] T. -H. Tsai et al., “A Cascaded PLL (LC-PLL + RO-PLL) with a Programmable Double Realignment Achieving 204fs Integrated Jitter (100kHz to 100MHz) and -72dB Reference Spur,” ISSCC, pp. 376-377, Feb. 2022.
> [3] C. Hwang et al., “A 188fsrms-Jitter and −243dB-FoMjitter 5.2GHz-Ring-DCO-Based Fractional-N Digital PLL with a 1/8 DTC-Range-Reduction Technique Using a Quadruple-Timing-Margin Phase Selector,” ISSCC, pp. 378-380, Feb. 2022.
> *high-Fref of 1.85GHz* \
> [4] Y. Jo et al., “A 135fsrms-Jitter 0.6-to-7.7GHz LO Generator Using a Single LC-VCO-Based Subsampling PLL and a Ring-Oscillator-Based Sub-Integer-N Frequency Multiplier,” ISSCC, pp. 76-77, Feb. 2023.
> 
> *PVT stable* \
> [5] H. Kim et al., “A Low-Jitter 8-GHz RO-Based ADPLL With PVT-Robust Replica-Based Analog Closed Loop for Supply Noise Compensation,” IEEE JSSC, vol. 57, no. 6, pp. 1712-1722, June 2022.
> [6] D. Turker et al., “A 7.4-to-14GHz PLL with 54fsrms jitter in 16nm FinFET for integrated RF-data-converter SoCs,” ISSCC, pp. 378-380, Feb. 2018.
