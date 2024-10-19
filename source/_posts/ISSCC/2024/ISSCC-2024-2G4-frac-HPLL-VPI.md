---
title: >-
  ISSCC-2024 14.7 A 0.45V 0.72mW 2.4GHz Bias-Current-Free Fractional-N Hybrid
  PLL Using a Voltage-Mode Phase Interpolator in 28nm CMOS
toc: true
tags:
  - ISSCC
  - 2024
  - PLL
  - PI
  - THU
abbrlink: 39088
date: 2024-10-19 22:30:11
---

![Keypoints](https://s21.ax1x.com/2024/10/19/pAaFqk6.png) \

##### Full Citation

L. Feng et al., "**14.7 A 0.45V 0.72mW 2.4GHz Bias-Current-Free Fractional-N Hybrid PLL Using a Voltage-Mode Phase Interpolator in 28nm CMOS**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 266-268, doi: 10.1109/ISSCC49657.2024.10454404.

[IEEE Link](https://ieeexplore.ieee.org/document/10454404) \

## Keypoints

- time-interleaving flip-flop phase detector (TI-FFPD)
  - high linearity and low reference spur
  - duty-cycle-based
- voltage-mode phase interpolator (VPI)
  - Q-noise cancellation
  - scales a stable reference voltage for the TCKV period
  - no gain calibration 
- HPLL
  - class-D D/VCO
  - frequency doubler (FD)
    - a duty-cycle correction (DCC) circuit
    - DTC and LMS delay cali.
  - feedback
    - MMD with retiming DFFs
    - interpolation window phi_A and phe_B with Tckv
  - prop. path
    - RS-latch-based FFPDs alternatively with appropriate polarity
    - resistor-based digital-to-analog converter (RDAC)
      - 7b segmented RDAC
      - 4b binary R-2R DAC and a 3b thermometer DAC
      - make voltages according to PICODE (SUM_FCW_FRAC)
      - the PICODE compensates frac-q-err
      - full scale of the RDAC tuned to adjust the PLL BW
    - second-order RC filter
  - intg. path
    - dual-BBPD structure
    - avoid BBPD gain degradation in fractional-N mode

## Background

- low-voltage clock generation and modulation
  - dynamic voltage scaling for low-power SoC
  - time domain at low supply voltage is challenging
    - high-performance phase detector (PD)
    - effective ΔΣ quantization noise (Q-noise) reduction
    - time resolution of a DTC is severely degraded as V--
  - voltage-domain compensation
    - lower noise
    - better linearity
    - first convert from phase to voltage
    - consumes significant voltage headroom
    - nonlinearity ++
  - on-chip voltage booster
  - large decoupling capacitors


<img src="https://s21.ax1x.com/2024/10/19/pAaFLtK.png" width = "500" alt="Overall architecture of the proposed HPLL with the TI-FFPD and VPI" align=center />

<img src="https://s21.ax1x.com/2024/10/19/pAaFOfO.png" width = "500" alt="Q-noise reduction method of DTC, voltage-domain compensation and proposed VPI" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  50 MHz \
**OUT**  2.4 GHz \
**REF SPUR**  -70.2 dBc \
**FRAC SPUR**  -57.7 dBc \
**POWER**  0.72 mW  \
**RMS JITTER**  590 fs \
**FOM**  -246 dB \

## Important References

> *integer-N PLL at 0.4* \
> [1] Z. Zhang et al., “A 0.4V-VDD 2.25-to-2.75GHz ULV-SS-PLL Achieving 236.6fsrms Jitter, −253.8dB Jitter-Power FoM, and −76.1dBc Reference Spur,” ISSCC, pp. 86-88, 2023.
> 
> *voltage-domain compensation* \
> [2] J. Kim et al., “A 104fsrms-Jitter and −61dBc-Fractional Spur 15GHz Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error Cancelation Technique,” ISSCC, pp. 448−449, 2021. \
> [3] L. Wu et al., “A Power-Efficient Fractional-N DPLL with Phase Error Quantized in Fully Differential-Voltage Domain,” IEEE JSSC, vol. 56, no. 4, pp. 1254–1264, 2021.
> 
> *on-chip voltage booster to supply* \
> [4] N. Pourmousavian et al., “A 0.5-V 1.6-mW 2.4-GHz Fractional-N All-Digital PLL for Bluetooth LE with PVT-Insensitive TDC Using Switched-Capacitor Doubler in 28-nm CMOS,” IEEE JSSC, vol. 53, no. 9, pp. 2572-2583, 2018.
> 
> *time-interleaving flip-flop phase detector (TI-FFPD)* \
> [5] L. Feng et al., “A Low-Voltage Bias-Current-Free Pseudo-Differential Hybrid PLL Using a Time-Interleaving Flip-Flop Phase Detector,” IEEE A-SSCC, pp. 1-3, 2023.
> 
> *frequency doubler (FD) with a duty-cycle correction (DCC) circuit* \
> [6] W. Wu et al., “A 14-nm Ultra-Low Jitter Fractional-N PLL Using a DTC Range Reduction Technique and a Reconfigurable Dual-Core VCO,” IEEE JSSC, vol. 56, no. 12, pp. 3756–3767, 2021.