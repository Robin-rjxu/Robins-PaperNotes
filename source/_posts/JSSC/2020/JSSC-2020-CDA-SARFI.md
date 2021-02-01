---
title: >-
  JSSC-2020 An 8-Bit 1-GS/s Asynchronous Loop-Unrolled SAR-Flash ADC With
  Complementary Dynamic Amplifiers in 28-nm CMOS
toc: true
tags:
  - JSSC
  - 2020
  - ADC
  - KAIST
abbrlink: 34595
date: 2021-02-01 20:14:14
---

![keypoints](https://api2.mubu.com/v3/document_image/3081f7cd-7998-4ad1-b8e5-f5ec18a88ea3-216525.jpg) \

##### Full Citation

D. -R. Oh, K. -J. Moon, W. -M. Lim, Y. -D. Kim, E. -J. An and S. -T. Ryu, "**An 8-Bit 1-GS/s Asynchronous Loop-Unrolled SAR-Flash ADC With Complementary Dynamic Amplifiers in 28-nm CMOS**," in IEEE Journal of Solid-State Circuits, doi: 10.1109/JSSC.2020.3044624.

[IEEE Link](https://ieeexplore.ieee.org/document/9311408) \

## Keypoints

- hybrid ADC: LU-SAR + flash
  - preamplifier shared by the LU-SAR and Interpolating-flash
  - complementary dynamic amplifier (CDA)
  - interpolation by 8 with embedded references
  - further shoot-through and unwanted latching
  - foreground offset and mismatch calibration

## Background

- high-speed medium resolution ADC
  - SAR
    - POSs: compactness, power efficiency; NEGs: limited speed
    - loop-unrolled (LU) : eliminate delay of logic and comparator reset
  - flash
    - fastest speed; hardware overhead
    - dynamic interpolation
      - NEGs: limited linearity

## Details

- compare with conventional DA and time-domian I-Flash AD
  - CDA: amplify when both charge and discharge, reuse the charge, no reset phase
  - time-domain interpolation: multiple reference voltages
- 4-BIT hybrid SAR + 4.5-bit I-Flash ADC, 5 cycles
  - P-input: charging, for SAR; N-input: discharging, for I-Flash
  - 8x interpolation, only 4 CDAs
- circuits
  - modified CDA
    - reduce kickback: stack transistors
    - eliminate memory effect: switches'
    - offset calibration: current cells
  - embedded references
    - CDA input size-mismatch ratio m:n
    - offset calibration
  - power: reduce shoot-through current(STP) and unwanted latching

![block diagram](https://api2.mubu.com/v3/document_image/18ae0b14-2117-4ca5-9efc-af14b2b5649e-216525.jpg) \

![CDA](https://api2.mubu.com/v3/document_image/5ff94b46-2e9a-4a70-b491-bdbbdef5d5b1-216525.jpg) \

## Conclusion

- **TECH** 28nm \
- **RES** 8-bit \
- **SAMPLING RATE** 1GS/s \ 
- **POWER** 2.55 mW@1.1V \
- **DNL** 0.59 LSB \
- **INL** 0.82 LSB \
- **SFDR** 59.4 dB \
- **SNDR** 45.5 dB \
- **ENOB** 7.26 \
- **FOM_W** 16.6 fJ/conv.-step \

## Important Reference
> *conference paper*
>
> - [14] D.-R. Oh, K.-J. Moon, W.-M. Lim, Y.-D. Kim, E.-J. An, and S.-T. Ryu, “An 8b 1GS/s 2.55 mW SAR-flash ADC with complementary dynamic amplifiers,” in Proc. IEEE Symp. VLSI Circuits, Jun. 2020, pp. 1–2. \
>
> *time-domain interpolating*
>
> - [12] D.-R. Oh, J.-I. Kim, D.-S. Jo, W.-C. Kim, D.-J. Chang, and S.-T. Ryu, “A 65-nm CMOS 6-bit 2.5-GS/s 7.5-mW 8× time-domain interpolating flash ADC with sequential slope-matching offset calibration,” IEEE J. Solid-State Circuits, vol. 54, no. 1, pp. 288–297, Jan. 2019. \
>
> *DA and CDA*
>
> - [15] D.-R. Oh, D.-S. Jo, K.-J. Moon, Y.-J. Roh, and S.-T. Ryu, “Powerefficient flash ADC with complementary voltage-to-time converter,” Electron. Lett., vol. 53, no. 12, pp. 772–773, Jun. 2017. \
> - [16] Q. Fan, R. Zhang, P. Bikkina, E. Mikkola, and J. Chen, “A 500 MS/s 10-bit single-channel SAR ADC with a double-rate comparator,” in Proc. ESSCIRC—IEEE 45th Eur. Solid State Circuits Conf. (ESSCIRC), Sep. 2019, pp. 193–196. \
