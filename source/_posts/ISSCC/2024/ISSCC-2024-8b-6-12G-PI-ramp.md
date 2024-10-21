---
title: >-
  ISSCC-2024 7.9 An 8b 6-12GHz 0.18mW/GHz DC Modulated Ramp-Based Phase
  Interpolator in 65nm CMOS Process
toc: true
tags:
  - ISSCC
  - 2024
  - PI
  - RO
  - WSU
abbrlink: 16479
date: 2024-10-21 23:01:18
---

![Keypoints](https://s21.ax1x.com/2024/10/21/pAdivH1.png) \

##### Full Citation

S. Mohapatra, E. Afshar, Z. Zhou and D. Heo, "**7.9 An 8b 6-12GHz 0.18mW/GHz DC Modulated Ramp-Based Phase Interpolator in 65nm CMOS Process**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 140-142, doi: 10.1109/ISSCC49657.2024.10454438.

[IEEE Link](https://ieeexplore.ieee.org/document/10454438) \

## Keypoints

- proposed ramp-based PI
  - 50% output
  - no need for extra quad generator and slew circuitry at inputs
  - mitigates the speed limitation and noise challenges
  - 4/2-phase output
  - technology scaling benefited
- 8b PI implementation
  - ramp generator
    - current bias with V-to-I loading SC
    - noise current is high-pass filtering
    - I_BIAS is prop to C_L
  - inverter-based comparator
    - V_TH tracking
    - feedback with op-amp to control current
  - 4-phase selection + 6b DAC
    - differential DC-modulated ramp signal
    - vary ±75 mV of inverter VTH
    - PWM outputs
  - pulse generator to create fixed-width pulse
  - up to 90 degree shift
  - injection-locked ring oscillator (ILRO)
  - output phases
    - 4 phases of the RO
    - 4-phase by the combined edge with XOR (2x frequency)
- noise consideration
  - SC in slope gen.
  - op-amp bandwidth
  - injection-locked filters the ramp generator noise
- ILRO frequency off-chip calibration

## Background

- multi-phase PI for CDR to sample time-interleaved ADCs
  - high precision
  - extra quad-generator
- PI for baseband beamforming system for large antenna arrays
  - wide signal bandwidth
  - high-speed
  - linear
  - fine-resolution
  - low power
- PI structure
  - quad generators at inputs
  - current/voltage mode PI
    - extra slew-rate control to have overlapped input
    - CMPI --> linearity issues
    - VMPI --> higher dynamic power
  - integrating mode PI
    - higher noise
    - slope varies a lot
  - ramp based PI
    - noisy with current source
    - high power due to static OPAMP-based CMP
    - limited operation speed
    - need DCC


<img src="https://s21.ax1x.com/2024/10/21/pAdizAx.png" width = "500" alt="the proposed PI architecture" align=center />

<img src="https://s21.ax1x.com/2024/10/21/pAdFSN6.png" width = "500" alt="comparison of the prior PIs and the proposed architecture" align=center />

## Conclusion

**TECH**  65 nm \
**FREQ**  6-12 GHz \
**INL**  1.7 LSB \
**DNL**  0.8 LSB \
**POWER**  2.2 mW  \
**JITTER**  68 fs \
**EFFICIENCY**  0.18 mW/GHz \

## Important References

> *ramp-based PI* \
> [1] S. Mohapatra et al., “Low-Power Process and Temperature-Invariant Constant Slope-and-Swing Ramp-Based Phase Interpolator,” IEEE JSSC, vol. 58, no. 8, pp. 2267-2277, Aug. 2023.
> 
> *current (CMPI)* \
> [2] Z. Wang and P. R. Kinget, “A 65nm CMOS, 3.5-to-11GHz, Less-Than-1.45LSB-INLpp, 7b Twin Phase Interpolator with a Wideband, Low-Noise Delta Quadrature Delay-Locked Loop for High-Speed Data Links,” ISSCC, pp. 292-294, Feb. 2022.
> 
> *voltage (VMPI)* \
> [3] S. Chen et al., “A 4-to-16GHz inverter-based injection-locked quadrature clock generator with phase interpolators for multi-standard I/Os in 7nm FinFET,” ISSCC, pp.390-392, Feb. 2018.
> 
> *integrating mode PI (IMPI)* \
> [4] A. K. Mishra et al., “A 9b-Linear 14GHz Integrating-Mode Phase Interpolator in 5nm FinFET Process,” ISSCC, pp. 294-295, Feb. 2022.
> 
> [5] Y.C. Huang and B.-J. Chen, “An 8b injection-locked phase rotator with dynamic multiphase injection for 28/56/112Gb/s Serdes application,” ISSCC, pp. 486–487, Feb. 2019.