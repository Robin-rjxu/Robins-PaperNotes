---
title: >-
  ISSCC-2024 7.4 A 0.027mm2 5.6-7.8GHz Ring-Oscillator-Based Ping-Pong Sampling PLL Scoring 220.3fsrms Jitter and -74.2dBc Reference Spur
toc: true
tags:
  - ISSCC
  - 2024
  - PLL
  - RO
  - SPD
  - UMacau
abbrlink: 45281
date: 2024-10-07 20:28:56
---

![Keypoints](https://s21.ax1x.com/2024/10/07/pAGQ2OH.md.png) \

##### Full Citation

Y. Huang, Y. Chen, Z. Yang, R. P. Martins and P. -I. Mak, "**7.4 A 0.027mm2 5.6-7.8GHz Ring-Oscillator-Based Ping-Pong Sampling PLL Scoring 220.3fsrms Jitter and -74.2dBc Reference Spur**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 130-132, doi: 10.1109/ISSCC49657.2024.10454291.

[IEEE Link](https://ieeexplore.ieee.org/document/10454291) \

## Keypoints

- dual-path RO-based PLL
  - ping-pong sampling phase detector (PP-SPD)
  - implicit Fref doubling behavior
  - extend loop BW
  - reduce SH delay to Tref/2
- separate integral path (I-path)
  - suppress the flicker noise
  - constrain the locking point within the high Kpd region
- edge correction loop (ECL)
  - correct delay of the ping-pong paths
  - adjusting the threshold of the inverter-based REF buffer
  - fast locking (<2.5μs)
- circuits
  - slope generator + SPD + gm
    - unit-gain buffer (UGB)
    - isolate sampling and hold capacitors
    - eliminate the charge-sharing effect
  - T-shape switches
    - mitigate ref feedthrough
    - dual-path share the same Vref
  - three-stage differential RO
    - two sets of varactors array for I/P-path respectively
  - tunable stacked REF buffer
    - two parallel branches
      - main branch
      - scaled assistant branch controlled by the ECL
    - lowering power consumption
    - ground disturbance

## Background

- RO-based PLL is promising for multi-lane applications
  - small footprint
  - wide tuning range
  - multi-phase generation
  - frequency-pulling resilience
- other schemes
  - ILCM / MDLL
  - suppress RO PN
  - increasing ref spur
  - complex calibration
- type-I PLL
  - high PD gain
    - wide bandwidth
    - good stability
      maximum 45 degree PM at 1/4 Fref
  - limited by Fref
- ref frequency multiplier
  - relieve BW-stability
  - slow digital calibration for duty cycle correction
- cascading PLL and delay-locked loop for noise cancellation
  - large PN filtering effect
  - high-frequency VCDL --> high power consumption
  - require off-chip gain calibration


<img src="https://s21.ax1x.com/2024/10/07/pAGQg6e.png" width = "500" alt="The proposed RO-Based PP-S-PLL" align=center />

## Conclusion

**TECH**  65 nm  \
**REF**  100 MHz \
**OUT**  5.6 ~ 7.8 GHz \
**REF SPUR**  -74.2 dBc \
**POWER**  16.47 mW  \
**RMS JITTER**  220.3 fs \
**FOM**  -241 dB \

## Important References

> *type-I PLL* \
> [3] L. Kong et al., “A 2.4 GHz 4 mW Integer-N Inductorless RF Synthesizer,” IEEE JSSC, vol. 51, no. 3, pp. 626–635, Mar. 2016.
> 
> *multi-phase ref generation* \
> [4] A. Khashaba et al., “A low-noise frequency synthesizer using multiphase generation and combining techniques,” IEEE JSSC, vol. 55, no. 3, pp. 592–601, Mar. 2020.
