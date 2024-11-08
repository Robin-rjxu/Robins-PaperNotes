---
title: >-
  CICC-2024 A 20-24-GHz DPSSPLL with Charge-Domain Bandwidth Optimization Scheme
  Achieving 61.3-fs RMS Jitter and -253-dB FoMJitter
toc: true
tags:
  - CICC
  - 2024
  - PLL
  - SSPD
  - HkUST
abbrlink: 5790
date: 2024-11-08 19:06:32
---

![Keypoints](https://s21.ax1x.com/2024/11/08/pAyXnzD.png) \

##### Full Citation

L. Wang, Z. Liu, R. Ma and C. P. Yue, "**A 20-24-GHz DPSSPLL with Charge-Domain Bandwidth Optimization Scheme Achieving 61.3-fs RMS Jitter and -253-dB FoMJitter**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529091.

[IEEE](https://ieeexplore.ieee.org/document/10529091) \

## Keypoints

- charge-domain gain and bandwidth control scheme
  - in P-path
    - fixed capacitor 8Cu
    - 3b capacitor bank
  - operation
    - sampled on both P/N side
    - neutralize P/N sides through SW
    - adjust P-path gain and BW
  - SSCP in the high-gain integral path
    - eliminate P/N common-mode voltage difference
    - minimize P/N offset
    - noise is attenuated by large RC
- dual-path subsampling PLL
  - differential-mode sampling
  - all passive switched-cap architecture
  - dominant prop path (P-path)
    - SH SSPD and dual-path
      - slow path
      - fast feedforward path
      - large capacitor (278f)
        - provide stability zero
        - enhance phase margin
    - charge neutralization-based passive gain/BW control
      - timing
        - sample and hold pulse (ɸSH)
        - loop filter pulse(ɸLF)
        - charge neutralization pulse (ɸCN)
      - control gain by adjust charge neutralization
      - neutralization causes voltage disturbance
      - suppress by RC in LPF
    - preserve ref PN
    - wide and adjustable PN
  - active integral path (I-path)
  - high-speed inductor-less TSPC divider
    - as pre-scaler
    - div-by-4 with 2 DFFs and an inverter
    - proper scaling to ensure correct pull down/up
    - sufficient driving current for optimal high-freq performance
  - compact layout with only on-chip loop filter

## Background

- advanced wireline and mmWave RX systems
  - high-performance PLLs
  - sub-100-fs jitter
- sampling PLL
  - high phase detector gain
  - optimum PN achieved with balance of ref and VCO
  - conventional type-II SSPLL
    - current domain gain/BW control
    - adjust the pulse width phe_CP
    - noisy
      - current
      - stability resistor Rz
    - off chip loop filter
  - conventional passive type-I SSPLL
    - remove charge pump and Rz
    - compact loop filter capcitors
    - voltage domain gain/BW control
      - rely on slope-control
      - compromise ref PN
      - limit PD gain

<img src="https://s21.ax1x.com/2024/11/08/pAyXeJK.png" width = "500" alt="System diagram of the proposed DPSSPLL" align=center />

<img src="https://s21.ax1x.com/2024/11/08/pAyXmRO.png" width = "500" alt="the proposed passive gain control scheme" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  250 MHz \
**OUT**  20 ~ 24 GHz \
**REF SPUR**  -44.1 dBc \
**POWER**  13.35 mW  \
**RMS JITTER**  61.23 fs \
**FOM**  -253 dB \

## Important References

> *sampling PLLs with high phase detector gain* \
> [1] Yang, Z. et al. “A 25.4-to-29.5GHz 10.2mW Isolated Sub-Sampling PLL Achieving -252.9dB Jitter-Power FoM and -63dBc Reference Spur,” ISSCC 2019. \
> [2] J. Lee et al., "A 16GHz 33fs rms Integrated Jitter FLL-less Gear Shifting Reference Sampling PLL," CICC 2023.
> 
> *SSCP in the integral path* \
> [3] L. Wang, et al., "A 24-30 GHz Cascaded QPLL Achieving 56.8-fs RMS Jitter and −248.6-dB FoMjitter," VLSI 2023.
> 
> *Charge-sharing lock+harm. extraction* \
> [4] Y. Hu et al., "17.6 A 21.7-to-26.5GHz Charge-Sharing Locking Quadrature PLL with Implicit Digital Frequency-Tracking Loop Achieving 75fs Jitter and −250dB FoM," ISSCC 2020.
> 
> *Charge-Steering ADPLL* \
> [5] W. Tao, et al., "An 18.8-to-23.3 GHz ADPLL Based on Charge-Steering-Sampling Technique Achieving 75.9 fs RMS Jitter and –252 dB FoM," VLSI 2023.
> 
> *CPPLL with high-speed CP*
> [6] S. Kalia et al., "A Sub-100 Fs RMSjitter 20 GHz Fractional-N Analog PLL with a BAW Resonator Based On-Chip 2.5 GHz Reference," JSSC 2022.