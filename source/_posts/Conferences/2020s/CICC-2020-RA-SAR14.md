---
title: CICC-2020 A 72.6 dB SNDR 14b 100 MSPS Ring Amplifier Based Pipelined SAR ADC with Dynamic Deadzone Control in 16 nm CMOS
toc: true
date: 2020-12-29 21:18:41
tags:
    - ADC
    - CICC
    - 2020
    - TSMC
---

![Keypoints](https://api2.mubu.com/v3/document_image/67e0dee3-2cc1-4b1c-8f67-23139fb25995-216525.jpg) \

##### Full Citation

M. Kinyua and E. Soenen, "**A 72.6 dB SNDR 14b 100 MSPS Ring Amplifier Based Pipelined SAR ADC with Dynamic Deadzone Control in 16 nm CMOS**," 2020 IEEE Custom Integrated Circuits Conference (CICC), Boston, MA, USA, 2020, pp. 1-4, doi: 10.1109/CICC48029.2020.9075921.
![IEEE Link]https://ieeexplore.ieee.org/document/9075921 \

## Keypoints

- a merged deadzone control circuit
  - dynamically control the offset embedded in the second-stage inverter
  - obviates the need to use high VTH devices
  - accomplish coarse estimation and fine settling of the output signal
- pipelined 14b(6+9) SAR ADC
  - half reference design
  - minimal fast SAR for decision cycling

## Background
- ring amplifier
  - inverter-based, wide-swing, high output resistance
  - stable when the amplifier input approaches the desired common-mode
    - operating the 3rd stage in deep subthreshold
    - high output resistance that forms a dominant pole for stable feedback operation.
- three-stage ring amplifier
  - dynamically embedded offset via a resistor RB in the second stage inverter
  - high threshold devices in the third stage to accomplish high gain

## Details

- **Principle of the dynamic deadzone control**
  - a compact input pair and a matching resistor RB regulate the VDZ by current mirroring
  - proper design trading of VRB, RB and inverter sizing
  - transient response of voltage (VRB) to accomplish coarse and fine amplification
- **Implementation**
  - RA: reduction in the number of stacked devices
  - 14b = 6b + 9b, half reference design to avoid capacitor scaling
  - asynchronous, SC-CMFB, minimal sized fast SAR for decision cycling

![proposed ring amplifier with deadzone control circuits](https://api2.mubu.com/v3/document_image/f7f9c1f3-2dac-488b-8be2-ea1698a93108-216525.jpg) \

![block diagram](https://api2.mubu.com/v3/document_image/33fca48e-80f7-4bc6-b188-ef7d7e19273a-216525.jpg) \

## Conclusion

- **TECH** 16nm
- **RES** 14-bit
- **SAMPLING RATE** 100MS/s
- **POWER** 2.5 mW@0.75/1.2 V
- **SFDR** 86.5 dB
- **SNDR** 72.6 dB
- **FOM_S** 175.6
- **FOM_W** 7.2 fJ/conv.-step

## Important Reference
>
>typical ring amplifier
>- [3] Y. Lim, and M. Flynn, “A 100 MS/s, 10.5 Bit, 2.46 mW Comparator-Less Pipeline ADC Using Self-Biased Ring Amplifiers,” IEEE J. Solid-State Circuits, vol. 50, no. 10, pp. 2331–2341, Oct. 2015. \
>
>fully-differential input stage, high Vth in the second and third stages
>
>- [4] Y. Lim, and M. Flynn, “A 1 mW 71.5 dB SNDR 50 MS/s 13 bit Fully Differential Ring Amplifier Based SAR-Assisted Pipeline ADC,” IEEE J. Solid-State Circuits, vol. 50, no. 12, pp. 2901–2911, Dec. 2015. \