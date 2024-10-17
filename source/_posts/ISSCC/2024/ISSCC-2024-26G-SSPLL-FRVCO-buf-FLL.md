---
title: ISSCC-2024 10.9 A 23.2-to-26GHz Sub-Sampling PLL Achieving 48.3fsrms Jitter, -253.5dB FoMJ, and 0.55μs Locking Time Based on a Function-Reused VCO-Buffer and a Type-I FLL with Rapid Phase Alignment
toc: true
tags:
  - ISSCC
  - 2024
  - SSPD
  - PLL
  - FLL
  - UMacau
abbrlink: 4277
date: 2024-10-17 22:07:03
---
![Keypoints](https://s21.ax1x.com/2024/10/17/pAUMmhn.png) \

##### Full Citation

H. Li, T. Xu, X. Meng, J. Yin, R. P. Martins and P. -I. Mak, "**10.9 A 23.2-to-26GHz Sub-Sampling PLL Achieving 48.3fsrms Jitter, -253.5dB FoMJ, and 0.55μs Locking Time Based on a Function-Reused VCO-Buffer and a Type-I FLL with Rapid Phase Alignment**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 204-206, doi: 10.1109/ISSCC49657.2024.10454298.

[IEEE Link](https://ieeexplore.ieee.org/document/10454298) \

## Keypoints

- type-II SSPLL
  - low-jitter and low-spur 
  - sub-us locking time (<64 ref cycles)
  - master-slave SSPD with constant Gm
    - isolate sampling from the VCO
    - sufficient PM with C_S1>7x C_S2
- function-reused(FR) VCO buffer
  - eliminate noise and capacitive load from the buffer
  - no inductor
  - transistor as buffer is merged into the negative gm transistor
    - naturally isolate the sampling from the tank
  - low spur and low jitter
    - decreasing RD and minimal C_S2
    - large SSPD gain
    - negligible PN degradation from RD
- source-to-gate(S2G) transformer-feedback(TF) VCO
  - superior PN and FoM
  - FR VCO buffer
  - isolate the nonlinear load capacitor from tank
  - reduce 1/f noise up-conversion
- fast frequency-locked loop (FLL)
  - not contribute to the PN
  - decouple locking time and initial phase error
  - rapid phase alignment
  - coarse-fine-TDC-based type-I loop for SC search
  - operation flow
    - step 1: phase aligner gates the DIV and delay fb CKD
    - step 2: CF-TDC config. the FLL as a type-I loop for SC search
    - step 3: SS loop without cycle slip 

## Background

- PLL with low jitter for high-speed wireless comm. 
  - <97fs at 26GHz for 5G FR2 using 256-QAM
  - robustly lock within sub-us
- previous low-jitter mm-wave PLL
  - sub-10G PLL + frequency multipliers
    - power- and area-hungry buffers
    - boost output power 
    - suppress subharmonic spurs
  - sub-sampling PLL
    - directly synthesizing an mm-wave LO
    - low in-band PN
    - wide BW to suppress VCO PN
    - ref spur with isolation VCO buffer
    - small capture range of SSPD : long SC search and weak loop settling
- previous FLL for SS-PLL
  - freq-cnt-based : slow with small frequency error
  - type-II loop with DZ :  limited and slow
  - cnt-and-TDC-based config as a type-I loop
    - high-power with the TDC at VCO rate
    - always-on FLL loop to monitor the loose lock


<img src="https://s21.ax1x.com/2024/10/17/pAUMK10.png" width = "500" alt="Overall architecture of the proposed SSPLL using an FR VCO-buffer and a type-I FLL with rapid phase alignment" align=center />

<img src="https://s21.ax1x.com/2024/10/17/pAUMupq.png" width = "500" alt="The locking chart flow, locking procedures, and locking time analysis of the proposed SSPLL" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  100 MHz \
**OUT**  23.2~26 GHz \
**REF SPUR**  -66 dBc \
**POWER**  19.1 mW  \
**RMS JITTER**  48.3 fs \
**FOM**  -253.5 dB \

## Important References

> *sub-10GHz PLLs with frequencymultipliers* \
> [1] J. Kim et al., “A 76fsrms Jitter and –40dBc Integrated-Phase-Noise 28-to-31GHz Frequency Synthesizer Based on Digital Sub-Sampling PLL Using Optimally Spaced Voltage Comparators and Background Loop-Gain Optimization,” ISSCC, pp. 258–259, Feb. 2019.
> 
> *power- and area-hungry buffers for boosting the output power and suppressing the subharmonic spurs*  \
> [2] X. Geng et al., “A 25.8GHz Integer-N PLL with Time-Amplifying Phase-Frequency Detector Achieving 60fsrms Jitter, -252.8dB FoMJ, and Robust Lock Acquisition Performance,” ISSCC, pp. 388–389, Feb. 2022. \
> [3] Y. Hu et al., “A 21.7-to-26.5GHz Charge-Sharing Locking Quadrature PLL with Implicit Digital Frequency-Tracking Loop Achieving 75fs Jitter and −250dB FoM,” ISSCC, pp.276-277, Feb. 2020.
> 
> *sub-sampling (SS) PLL* \
> [4] X. Gao et al., “A Low Noise Sub-Sampling PLL in which Divider Noise is Eliminated and PD/CP Noise is Not Multiplied by N2,” IEEE JSSC, vol. 44, no. 12, pp. 3253-3263, Dec. 2009.
> 
> *SSPLL has inferior reference (ref.) spur* \
> [5] Z. Yang et al., “A 25.4-to-29.5GHz 10.2mW Isolated Sub-Sampling PLL Achieving -252.9dB Jitter-Power FoM and -63dBc Reference Spur,” ISSCC, pp. 270-271, Feb. 2019.
> 
> *source-to-gate (S2G) transformer-feedback (TF) VCO* \
> [6] C. Fan et al., “A 9mW 54.9-to-63.5GHz Current-Reuse LO Generator with a 186.7dBc/Hz FoM by Unifying a 20GHz 3rd-Harmonic-Rich Current-Output VCO, a Harmonic-Current Filter and a 60GHz TIA,” ISSCC, pp. 282-283, Feb. 2020.
> 
> *ferror is within two times of the fBW, there is no cycle slip* \
> [7] Y.-H. Liu et al., “An Ultra-Low Power 1.7-2.7 GHz Fractional-N Sub-Sampling Digital Frequency Synthesizer and Modulator for IoT Applications in 40 nm CMOS,” IEEE TCAS-I, vol. 64, no. 5, pp. 1094-1105, May 2017.