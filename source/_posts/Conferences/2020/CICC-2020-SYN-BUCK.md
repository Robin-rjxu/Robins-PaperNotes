---
title: >-
  CICC-2020 A Fully Synthesized Integrated Buck Regulator with Auto-generated
  GDS-II in 65nm CMOS Process
toc: true
tags:
  - Power
  - Buck
  - CAD
  - CICC
  - 2020
  - GIT
abbrlink: 8136
date: 2020-12-30 14:51:03
---

![keypoints](https://api2.mubu.com/v3/document_image/a5c28186-cd14-4888-832b-cca1ce5aa14f-216525.jpg) \

##### Full Citation

  - V. C. Krishna Chekuri, N. M. Rahman, E. Lee, A. Signh and S. Mukhopadhyay, "**A Fully Synthesized Integrated Buck Regulator with Auto-generated GDS-II in 65nm CMOS Process**," *2020 IEEE Custom Integrated Circuits Conference (CICC)*, Boston, MA, USA, 2020, pp. 1-4, doi: 10.1109/CICC48029.2020.9075924.
[IEEE Link](https://ieeexplore.ieee.org/document/9075924)

## Keypoints

  - flexible precision feedback loop
    - high-precision low-frequency mode
    - low-precision high-frequency mode
  - fully synthesized generation
    - pcell + macro + auto PR
    - design space exploration and reduced sets

## Background

  - inductive voltage regulator (IVR)
    - for fine-grain power management
    - fast dynamic voltage scaling
    - reduce power noise
    - reduce complexity by synthesizable loop

## Details

  - flexible precision feedback loop
    - high-precision low-frequency mode (6b, 2xFSW)
    - low-precision high-frequency mode (4b, 4xFSW)
  - synthesizable blocks
    - ADC
      - input voltage controlled delay line and latch
      - count the number of ones
      - re-configure to different precision and frequency
        - different pulse width
        - restrict the number of stages
        - bit shedding
    - DPWM
      - tri-state buffers and DLL
      - a mux selects phases by the compensators
  - on-chip autotuning engine
    - use a cost metric summing aggregated absolute error values
  - auto-generation tool
    - power stage: multiple custom pcells
    - loop: standard cell based synthesis
    - top: automated place and route; coupled back/front-end optimization
    - mixed-signal design space exploration
      - extend design space: IRV, controller, RTL, physical design, including digital parameters
      - reduce set: timing closure, target settling time, defined constraints

![overall architecture](https://api2.mubu.com/v3/document_image/aa791a4e-ead0-4fa4-bc46-bbf6640dc355-216525.jpg) \

![auto-generation tool flow](https://api2.mubu.com/v3/document_image/e8dbeea1-ac6f-4669-9e8c-429b9e6625c2-216525.jpg) \

## Conclusion

  - **TECH** 65nm
  - **VIN** 0.9~1.2 V
  - **VOUT** 0.6~1 V
  - **F_SW** 80~120 MHz
  - **L_LOAD** 62 nH
  - **C_LOAD** 23 nF
  - **PEAK EFFICIENCY** 157 uW@1.1V
  - **RESPONSE TIME** 200 ns@ΔI=30mA
  - **VOLTAGE RAMP** 130 mV/250 ns

## Important Reference
>*automated tool flow* 
> 
> - [2] V. C. Krishna Chekuri, N. Dasari, A. Singh and S. Mukhopadhyay, "Automatic GDSII Generator for On-Chip Voltage Regulator for Easy Integration in Digital SoCs," 2019 IEEE/ACM International Symposium on Low Power Electronics and Design (ISLPED), Lausanne, Switzerland, 2019, pp. 1-6, doi: 10.1109/ISLPED.2019.8824797.  [IEEE Link](https://ieeexplore.ieee.org/document/8824797) \
> 
>*a lightweight all-digital auto-tuner for post-silicon tuning the PID coefficients*
> 
>- [3] M. Kar, A. Singh, A. Rajan, V. De and S. Mukhopadhyay, "An All-Digital Fully Integrated Inductive Buck Regulator With A 250-MHz Multi-Sampled Compensator and a Lightweight Auto-Tuner in 130-nm CMOS," in IEEE Journal of Solid-State Circuits, vol. 52, no. 7, pp. 1825-1835, July 2017, doi: 10.1109/JSSC.2017.2693243. [IEEE Link](https://ieeexplore.ieee.org/document/7947104) \
> 