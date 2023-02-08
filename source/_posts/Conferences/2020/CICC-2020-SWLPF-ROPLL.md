---
title: >-
  CICC-2020 A 0.5V-to-0.9V 0.2GHz-to-5GHz Ultra-Low-Power Digitally-Assisted
  Analog Ring PLL with Less Than 200ns Lock Time in 22nm FinFET CMOS Technology
toc: true
tags:
  - PLL
  - CICC
  - 2020
  - Intel
abbrlink: 23879
date: 2021-01-01 16:17:45
---

![keypoints](https://api2.mubu.com/v3/document_image/ab546327-2a7e-42bc-aa5c-a98fb4672596-216525.jpg) \

##### Full Citation
B. Xiang, Y. Fan, J. Ayers, J. Shen and D. Zhang, "**A 0.5V-to-0.9V 0.2GHz-to-5GHz Ultra-Low-Power Digitally-Assisted Analog Ring PLL with Less Than 200ns Lock Time in 22nm FinFET CMOS Technology**," 2020 IEEE Custom Integrated Circuits Conference (CICC), Boston, MA, USA, 2020, pp. 1-4, doi: 10.1109/CICC48029.2020.9075897.
[IEEE Link](https://ieeexplore.ieee.org/document/9075897) \

## Keypoints
  - analog charge pump based loop
    - tunable switched capacitor loop filter
    - power gated charge pump bias
  - RO
    - V-F linearization by source degeneration
    - VCO startup circuit

## Background
  - maximum energy efficiency for SOC and IoT: ring oscillator
    - wide voltage/frequency range
    - rapid wake up
    - compact area

## Details
  - tunable switched capacitor loop filter
    - proportional capacitor Cp1/Cp2 + integral capacitor C1
    - swcaps act as a effective resistance
      - require no precision resistor
    - swap capacitor top/bottom plate to cancel out proportional volatge
      - require no reset voltage
    - split into charge pump and reset events to two phases
      - reduce large ripple
      - maintain proportional voltage for only half cycle
      - smaller Cp
    - tunable Cp banks
      - support different reference clock
  - VCO startup circuit
    - reset VCTL0 to VCC when the VCO is turned off
    - start pulling down VCTL0
    - TIMER cnt
    - turn on charge pump bias

![tunable switched capacitor loop filter](https://api2.mubu.com/v3/document_image/b67f38be-4cd3-4491-9998-841e1a22fd99-216525.jpg) \

## Conclusion
  - **TECH** 22nm \
  - **REF** 20~200 MHz \
  - **OUT** 0.2~5 GHz \
  - **POWER** 0.628 mW @ 0.8 V, 3.2GHz \
  - **RMS JITTER** 2.3 ps \
  - **FOM** -234.4 dB \


## Important Reference
>*sample-reset loop filter (SR-LPF)*
> 
> - [4] Y. Fan, et al, “Digital Leakage Compensation for a Low-Power and Low Jitter 0.5-to-5GHz PLL in 10nm FinFET CMOS Technology”, ISSCC, pp. 320-321, Feb. 2019. \
> 
> - [5] K. Shen, et al, “A 0.17-to-3.5mW 0.15-to-5GHz SoC PLL with 15dB Build-In Supply Noise Rejection and Self-Bandwidth Control in 14nm CMOS”, ISSCC, pp. 330-331, Feb. 2016. \
> 
> *switched capacitor loop filter (SC-LPF)*
> 
> - [10] H. Lee, et al, “A Scalable Sub-1.2mW 300MHz-to-1.5GHz Host-Clock PLL for System-on-Chip in 32nm CMOS”, ISSCC, pp. 96-97, Feb. 2011. \
