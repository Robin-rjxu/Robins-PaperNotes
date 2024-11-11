---
title: CICC-2024 A 29 GHz Sub-Sampling PLL with 25.6-fs-rms RJ based on a Discrete-Time Integrating PD in 45nm RF SOI
toc: true
tags:
  - CICC
  - 2024
  - PLL
  - SSPD
  - UUtah
abbrlink: 22571
date: 2024-11-11 19:26:13
---

![Keypoints](https://s21.ax1x.com/2024/11/11/pAcuXVA.png) \

##### Full Citation

R. Bindiganavile, A. Wahid and A. Tajalli, "**A 29 GHz Sub-Sampling PLL with 25.6-fs-rms RJ based on a Discrete-Time Integrating PD in 45nm RF SOI**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529069.

[IEEE Link](https://ieeexplore.ieee.org/document/10529069) \

## Keypoints

- discrete-time integrating phase detector (DTPD)
  - double phase PD
    - P/N type for falling/rising edges : ref DCC
    - support single/double phases mod
  - produces the error signal by directly taking the VCO output
  - programmable gain --> loop dynamics
  - 2 cascade discrete-time integrators
  - high-gain low-noise differential phase detector
- compact single-coil Phase Locked Loop (PLL)
  - sub-sampling achitecture
  - low-power and low jitter
  - operate at full rate
  - no need for any frequency division
- circuits
  - discrete-time integrating phase detector (DTPD)
    - 2 independent 6b DAC sets the DC bias voltage
    - output voltage is proportional to the phase error
    - 3 stages
      - first stage :second stage : discrete-time integrator
      - second stage : hold the signal for half period
      - third stage : gm cell
    - high gain with high instantaneous current
    - low power with the low average current
  - matchted VCO and a VCO-buffer pair
    - LC VCO based on SiGe core cross-coupled devices
      - MIM cap bank for 4G tuning range
      - 80um single-turn coil
    - programmable tail resistor bank tuning bias current
    - regulated supply
    - core BTJ buffers for sampling and driving RF probe
  - reconfigurable DTPD
    - DTPD circuit switched to double-phase structure
    - enhance updating rate
    - improve stability issues
  - Frequency Lock Assist (FLA)
    - well-defined dead zone (DZ)
    - turn off after freq lock is acquired

## Background

- low-jitter clock generation
  - modern communication and computing systems
  - 5G and beamforming systems
  - high-speed data converters
  - compact single-coil subsampling PLL

<img src="https://s21.ax1x.com/2024/11/11/pAcuqDH.png" width = "500" alt="The proposed PLL block diagram" align=center />

<img src="https://s21.ax1x.com/2024/11/11/pAcuLbd.png" width = "500" alt="circuit implementation" align=center />

## Conclusion

**TECH**  45 nm SiGe RF SOI \
**REF**  250/1000 MHz \
**OUT**  25 ~ 29 GHz \
**REF SPUR**  -28/-53 dBc \
**POWER**  21.4 mW  \
**RMS JITTER**  95/25.6 fs \
**FOM**  -247/-258.5 dB \

## Important References

> *sub-50 fs clock for high-speed data converter* \
> [1] S. S. Kumar et al., “A 750mW 24GS/s 12b Time-Interleaved ADC for Direct RF Sampling in Modern Wireless Systems” ISSCC, 2023. \
> [2] D. Turker et al., “A 7.4-to-14GHz PLL with 54fsrms jitter in 16nm FinFET for integrated RF-data-converter SoCs,” ISSCC, 2018.
> 
> *high-performance PLLs* \
> [3] Y. Hu et al., “17.6 A 21.7-to-26.5GHz Charge-Sharing Locking Quadrature PLL with Implicit Digital Frequency-Tracking Loop Achieving 75fs Jitter and −250dB FoM,” ISSCC, 2020. \
> [4] W. Chen et al., “A 21.8-41.6GHz Fast-Locking SS-PLL with Dead Zone Automatic Controller Achieving 62.7-fs Jitter and −250.3dB FoM,” RFIC, 2022. \
> [5] Y. Zhao et al., “A 20-GHz PLL with 20.9-fs Random Jitter,” JSSC, 2023. \
> [6] R. Bindiganavile et al., “A 59-fs-rms 35-GHz PLL with FoM of −241-dB in 0.18−μm BiCMOS/SiGe Technology,” RFIC, 2022.