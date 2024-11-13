---
title: >-
  CICC-2024 A 7.9 ps Resolution, Multi-Event TDC Using an Ultra-Low Static Phase
  Error DLL and High Linearity Time Amplifier for dToF Sensors
toc: true
tags:
  - CICC
  - 2024
  - TDC
  - TA
  - DLL
  - XIDIAN
abbrlink: 35172
date: 2024-11-14 06:58:30
---

![Keypoints](https://s21.ax1x.com/2024/11/14/pAgaai8.png) \

##### Full Citation

X. Wang et al., "**A 7.9 ps Resolution, Multi-Event TDC Using an Ultra-Low Static Phase Error DLL and High Linearity Time Amplifier for dToF Sensors**," 2024 IEEE Custom Integrated Circuits Conference (CICC), Denver, CO, USA, 2024, pp. 1-2, doi: 10.1109/CICC60959.2024.10529104.

[IEEE Link](https://ieeexplore.ieee.org/document/10529104) \

## Keypoints

- take aways
  - coarse/fine structure with residue generation
  - arbiter (replace DFF) circuits
  - cnt synchronization to avoid setup/hold violation
  - TA circuits
    - current discharge based
    - linearity improvement with offset
  - flash TDC
    - differential structure
    - symmetric delay line
    - identical driving/loading
    - comparison with reverse polarity
  - DLL
    - procedure to reduce static phase error
    - dual path : wo/wi TA
    - switch to TA path after locked
- coarse-fine interpolation scheme
  - interpolator recycling technique
  - reuses the Start channel to achieve the interleaving
- multi-event TDC
  - two coarse interpolation channel
    - a 4-bit interpolator
    - residue time generation (RTG) circuit
    - differential arbiter
      - higher sensitivity
      - eliminate the asymmetric input load of DFFs
    - inverter array to detect pattern of the one-hot code
  - residue time generator (RTG)
    - 16-channel RTG cells
    - gated by the interpolated signals
    - keep the TA within a better linearity input range
  - 16x TA
    - open-loop
    - gain of TA depends on the ratio of fast/slow current
    - Toff time to stabilize the discharging current
    - alleviates the nonlinearity induced by the charge-injection effect
  - 10-bit continuous counter
    - CNT synchronizer
    - eliminate the misalignment error
    - ensure a sufficient setup or hold time
  - ultra-low SPE(static phase error) DLL
    - 16 interpolation clocks
    - eliminate the stuck or harmonic lock problem
      - false lock protection
      - Start Control
    - SR latch based TA before the PFD
  - fine TDC
    - 5-bit flash TDC 
    - with 1-bit for the redundancy
    - shared between two coarse interpolation channels
    - fully symmetric delay line
    - differential voltage-controlled delay cell (VCDC)

## Background

- not quite understand the application (multi-event)
  - event number ?
  - how to achieve unlimited event number?
  - why need counter?
  - what is the limitation of previous work ?
- SPAD-based dToF sensors
  - Time-Correlated Single Photon Counting (TCSPC)
  - accurately determine the ToF information
- multi-event TDC
  - low dead time
  - mitigate the pile-up distortion
  - linear-mode dToF sensors
  - high TDC resolution
- previous works
  - histogramming TDC
    - high conversion rate
    - resolution is limited by the gate delay
  - interpolator multi-event TDC
    - deteriorated linearity
    - only one interpolator
  - TA+TDC
    - high resolution
    - only one photon event during one laser cycle
  - interleaving multi-event
    - maximum event number is limited by channels

<img src="https://s21.ax1x.com/2024/11/14/pAgatdP.png" width = "700" alt="TDC circuits 12" align=center />

<img src="https://s21.ax1x.com/2024/11/14/pAgaNIf.png" width = "700" alt="TDC circuits 34" align=center />

## Conclusion

**TECH**  0.18 um \
**RATE**  80 MHz \
**RES**  7.9 ps \
**RANGE**  2033.5 ns \
**DNL**  -0.25/0.35 LSB \
**INL**  -1.25/1.14 LSB \
**POWER**  10.8 mW  \

## Important References

> *histogramming TDC to 14GS/s but limited resolution* \
> [1] N. A. W. Dutton et al., ISSCC, 2015.
> 
> *one interpolator and undesired resolution* \
> [2] S. Zhuo et al., JSSC, 2023.
> 
> *high-res TDC with calibration-free TA but only one event* \
> [3] P. Keränen et al., TCAS-I, 2019.
> 
> *multi-event with interleaving operation* \
> [4] A. R. Ximenes, et al., JSSC, 2019. (10-bit continuous counter) \
> [5] C. Zhang, et al., JSSC, 2019.