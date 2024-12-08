---
title: >-
  ESSERC-2024 A Multi-Phase Injection-Locked 8-Phase 17 GHz Clock Generator with
  6b Phase Rotation for Multi-Phase Wireline Receivers
toc: true
tags:
  - ESSERC
  - 2024
  - MPCG
  - ILRO
  - UCBerkely
abbrlink: 52828
date: 2024-12-08 17:05:56
---

![Keypoints](https://s21.ax1x.com/2024/12/08/pA7WsDU.png) \

##### Full Citation

B. Zhou and B. Nikolić, "**A Multi-Phase Injection-Locked 8-Phase 17 GHz Clock Generator with 6b Phase Rotation for Multi-Phase Wireline Receivers**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 629-632, doi: 10.1109/ESSERC62670.2024.10719579.

[IEEE Link](https://ieeexplore.ieee.org/document/10719579) \

## Keypoints

- proposed multi-phase injection
  - phase rotation on the reference side
    - instead of the output side
    - avoid multiple rotators
    - rotate all phases at once
  - principle
    - injection the adjacent 2 stages
    - phase lock shift progressively
    - as the injection current assignment
    - trade-off between jitter and resolution
      - low jitter
      - high injection strength
      - high  phase error
      - worse resolution
      - noise is expected to be less than resolution
  - modeling
    - ILRO : cascaded delay cells and negatively feedback
    - injection stage
      - phase interpolator
      - two adjacent injection cell --> the same typical delay
    - non-injection stage : delay cell
    - typical delay without injection
    - total period --> injection clock period
    - injection locked
      - solving for the injection phase
      - yields the correct stage delay
- implementation
  - 4-stage differential CML-based ILRO
    - 5 NMOS differential pairs
      - maintain the same current
      - always-on primary pair (x1)
      - injection pairs with flipped polarity (x2)
      - each injection pairs is complemented with a pair (x2)
    - injection ratio is set by the current ratio
    - inject into two adjacent stages simultaneously
    - ring oscillator with injectors in each stage
  - DAC controls injection current
    - 8-step
    - linearly control
    - capable for dynamic test (continuous rotation)
  - replica buffers
  - replica bias
  - c2c output buffers
  - 8:2 mux for test

## Background

- Next-generation hyperscale computers
  - significant boosts in datacenter network bandwidth
  - faster high-speed wireline systems
  - high throughput in wireline receivers
    - Multi-phase sampling
    - maintaining the per-lane data rate
    - interleaving multiple lanes
    - clock are a large part of the wireline power budget
- previous work multi-phase clocks for wireline
  - used 8 or  more clock phases
  - highly sensitive to clock jitter
    - high-loss channels
    - the receiver eye is significantly degraded
  - Sampling phase alignment
    - performed on all the generated phases
    - high resolution
    - compensate for the degraded eye
    - scheme
      - multi-phase clock generation (MPCG)
        - injection-locked ring oscillator (ILRO)
        - phase-locked loop (PLL)
      - phase rotator
        - phase interpolator
        - each phase needs a additional PI
  - ILRO-based MPCG MPI
    - cascade multiple MPCGs
    - inject all generated phases
    - improving MPCG phase alignment and jitter filtering

<img src="https://s21.ax1x.com/2024/12/08/pA7WruT.png" width = "500" alt="Implemented phase rotator system architecture" align=center />

<img src="https://s21.ax1x.com/2024/12/08/pA7WBvV.png width = "500" alt="injection oscillator model" align=center />

## Conclusion

**TECH**  16 nm \
**FREQ**  17 GHz \
**PHASE**  8 \
**RES**  6 bits \
**INL**  4.05 LSB \
**DNL**  1.26 LSB \
**POWER**  33.6 mW  \
**RMS JITTER**  98 fs \
**PLL FOM**  -244.9 dB \
**MPCG FOM**  -266.2 dB \

## Important References

> *cascade multiple MPCGs and inject all generated phases (PI)* \
> [1] Z. Wang, et. al., ”11.4 A High-Accuracy Multi-Phase Injection-Locked 8-Phase 7GHz Clock Generator in 65nm with 7b Phase Interpolators for High-Speed Data Links,” ISSCC, 2021.
> 
> *MPI by injection assignment* \
> [2] M. Hossain and A. Chan Carusone, ”7.4 Gb/s 6.8 mW Source Synchronous Receiver in 65 nm CMOS,” JSSC, 2011. \
> [5] Y. -C. Huang and B. -J. Chen, ”30.7 An 8b Injection-Locked Phase Rotator with Dynamic Multiphase Injection for 28/56/112Gb/s Serdes Application,” ISSCC, 2019.
> 
> *time-modulated solutions* \
> [3] F. O’Mahony, et. al., ”A programmable phase rotator based on time-modulated injection-locking,” VLSI, 2010. \
> [4] Y. F. Zhang, J. Liang and T. C. Carusone, ”Design Considerations for Time-Modulated Injection-Locked Phase Interpolators and Rotators,” ISCAS, 2023.
> 
> *PI-based MPCG* \
> [6] S. Chen et al., ”A 4-to-16GHz inverter-based injection-locked quadrature clock generator with phase interpolators for multi-standard I/Os in 7nm FinFET,” ISSCC, 2018.
> 
> *trade-off between jitter and resolution (injection strength) * \
> [7] B. Razavi, ”A study of injection locking and pulling in oscillators,” JSSC, vol. 39, no. 9, pp. 1415-1424, Sept. 2004.
> 
> *Intel 16 process* \
> [8] Q. Yu et al., ”mmWave and sub-THz Technology Development in Intel 22nm FinFET (22FFL) Process,” IEDM, 2020.
> 
> *open-source circuit generation* \
> [9] BAG ILROPR. [Online].Available: https://github.com/ucb-art/bag ilropr