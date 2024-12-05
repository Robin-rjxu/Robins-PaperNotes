---
title: >-
  ESSERC-2024 A Compact 21-25 GHz Charge-Domain Fractional-N ADPLL with 168 fs
  Total RMS Jitter
toc: true
tags:
  - ESSERC
  - 2024
  - DPLL
  - ADC-PD
  - SPD
  - USTC
abbrlink: 15796
date: 2024-12-05 06:52:28
---

![Keypoints](https://s21.ax1x.com/2024/12/05/pAobsJg.png) \

##### Full Citation

W. Tao, Y. Liu, Y. Yang, R. B. Staszewski, F. Lin and Y. Hu, "**A Compact 21-25 GHz Charge-Domain Fractional-N ADPLL with 168 fs Total RMS Jitter**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 693-696, doi: 10.1109/ESSERC62670.2024.10719460.

[IEEE Link](https://ieeexplore.ieee.org/document/10719460) \

## Keypoints

- fractional-N charge-steering sampling (CSS) PD
  - phase error detection
    - pseudo-diff-pair
    - driven by the reference sinusoidal waveform
    - C-DAC compensates the frac phase error
    - capacitor bank is merged with the SAR-ADC
  - wider linear detection range : Tosc/8 --> Tref/8
  - recover the low KTD
    - mid-rise encoder
    - boost PD gain
    - maintain the multi-bit
    - mitigate the overly long locking and narrow detection range
  - operational principles
    - feedback clk_div triggers the charge-sample the sinusoidal Vref
    - preset the top plates to VDD
    - reset the bottom plates to VSS
    - sample to the top plates by the pseudo-diff-pair
    - switching part of Cfrac to compensate QE
- mmW fractional-N ADPLL based on the CSS-PD
  - proposed CSS-PD
  - SAR-ADC + fractional-N C-DAC
  - digital loop filter (DLF)
    - mid-rise encoder (MRE)
    - digital dead-zone (DZ) in the integral path
  - DIV
    - high-speed current-mode logic (CML) divider
    - multi-modulus divider (MMDIV)
    - ∆Σ modulator (DSM)
    - digital logic
  - DCO
  - C-DAC gain calibration

## Background

- 5G/6G mmW communications
  - mmW fractional-N frequency synthesizers
  - low total rms jitter
- frac PLL implementation
  - quantization noise from DSM-DIV
    - charge-pump PLL
    - DTC
      - analog loop
      - digital loop
      - intrinsic PN and nonlinearty
      - various calibration and mitigation
    - VDAC
  - low-jitter but integer-N
    - subsampling
    - charge-steering (sub-)sampling
    - sampling of a sharp RC-conditioned reference slope
    - time-interleaved multi-reference sampling
    - bang-bang phase detector

<img src="https://s21.ax1x.com/2024/12/05/pAob0df.png" width = "500" alt="Architecture of the proposed charge-domain fractional-N ADPLL based on a charge-steering sampling technique" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pAobrFS.png" width = "500" alt="proposed fractional-N reference sampling with capacitive (C)-DAC compensation" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pAobBo8.png" width = "500" alt="Vref with mid-rise encoder" align=center />

## Conclusion

**TECH**  22 nm \
**REF**  250 MHz \
**OUT**  21 ~ 25 GHz \
**REF SPUR**  -60 dBc \
**FRAC SPUR**  -46 dBc \
**POWER**  13.81 mW  \
**RMS JITTER**  168.2 fs \
**FOM**  -244.1 dB \

## Important References

> *charge-pump PLL with ∆Σ modulator (DSM)-controlled divider* \
> [1] S. Ek et al., “A 28-nm FD-SOI 115-fs Jitter PLL-Based LO System for 24–30-GHz Sliding-IF 5G Transceivers,” in IEEE J. Solid-State Cir., vol. 53, no. 7, pp. 1988-2000, July 2018.
> 
> *analog PLLs with DTC* \
> [2] W. Wu et al., “A 14-nm Ultra-Low Jitter Fractional-N PLL Using a DTC Range Reduction Technique and a Reconfigurable Dual-Core VCO,” in IEEE J. of Solid-State Cir., vol. 56, no. 12, pp. 3756-3767, Dec. 2021. \
> [3] P. T. Renukaswamy et al., “4.1 A 16GHz, 41kHzrms Frequency Error, Background-Calibrated, Duty-Cycled FMCW Charge-Pump PLL,” IEEE ISSCC, 2023, pp. 74-76. \
> [4] N. Markulic et al., “A DTC-Based Subsampling PLL Capable of Self-Calibrated Fractional Synthesis and Two-Point Modulation,” in IEEE J. of Solid-State Cir., vol. 51, no. 12, pp. 3078-3092, Dec. 2016.
> 
> *digital PLLs with DTC* \
> [5] L. Grimaldi et al., “16.7 A 30GHz Digital Sub-Sampling Fractional-N PLL with 198fsrms Jitter in 65nm LP CMOS,” 2019 IEEE ISSCC, San Francisco, CA, USA, 2019, pp. 268-270. \
> [6] G. Castoro et al., “4.5 A 9.25GHz Digital PLL with Fractional-Spur Cancellation Based on a Multi-DTC Topology,” IEEE ISSCC, 2023, pp. 82-84. \
> [7] V. K. Chillara et al., “9.8 An 860uW 2.1-to-2.7GHz all-digital PLL-based frequency modulator with a DTC-assisted snapshot TDC for WPAN (Bluetooth Smart and ZigBee) applications,” IEEE ISSCC, 2014, pp. 172-173.
> 
> *frac PLL with DAC* \
> [8] J. Kim et al., “32.4 A 104fsrms-Jitter and -61dBc-Fractional Spur 15GHz Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error Cancelation Technique,” 2021 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2021, pp. 448-450. \
> [9] X. Shen et al., “A 4-12.1-GHz Fractional-N Ring Sampling PLL Based on Adaptively-Biased PD-Merged DTC Achieving -37.6±0.9- dBc Integrated Phase Noise, 261.9-fs RMS Jitter, and -240.6-dB FoM,” ESSCIRC 2023- IEEE 49th European Solid State Circuits Conference (ESSCIRC), Lisbon, Portugal, 2023, pp. 257-260.
> 
> *sub-samplign PLL* \
> [10] H. Li, T. Xu, X. Meng, J. Yin, R. P. Martins and P. -I. Mak, “10.9 A 23.2-to-26GHz Sub-Sampling PLL Achieving 48.3fsrms Jitter, -253.5dB FoMJ, and 0.55us Locking Time Based on a Function-Reused VCO-Buffer and a Type-I FLL with Rapid Phase Alignment,” 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 204-206.
> 
> *charge-steering (sub-)sampling* \
> [11] W. Tao, W. Zhao, R. B. Staszewski, F. Lin and Y. Hu, “An 18.8-to-23.3 GHz ADPLL Based on Charge-Steering-Sampling Technique Achieving 75.9 fs RMS Jitter and –252 dB FoM,” 2023 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Kyoto, Japan,2023, pp. 1-2. 
> 
> *multi-reference sampling* \
> [12] H. Liu, W. Deng, H. Jia, S. Zhang, S. Sun and B. Chi, “A 4.8-GHz Time-Interleaved Multi-Reference PLL with 16.1-fs Jitter,” ESSCIRC 2023- IEEE 49th European Solid State Circuits Conference (ESSCIRC), Lisbon, Portugal, 2023, pp. 261-264.