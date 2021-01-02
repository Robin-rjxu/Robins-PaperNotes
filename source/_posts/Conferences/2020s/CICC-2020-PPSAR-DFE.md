---
title: CICC-2020 A 77.1-dB 6.25-MHz-BW Pipeline SAR ADC with Enhanced Interstage Gain Error Shaping and Quantization Error Shaping
toc: true
date: 2021-01-01 16:27:22
tags:
	- ADC
	- CICC
	- 2020
	- UTAustin
---

![keypoints](https://api2.mubu.com/v3/document_image/c7d5a9ff-6292-4809-bbeb-77a37fb23a1f-216525.jpg)

##### **Full Citation**

C. Hsu et al., "**A 77.1-dB 6.25-MHz-BW Pipeline SAR ADC with Enhanced Interstage Gain Error Shaping and Quantization Error Shaping**," 2020 IEEE Custom Integrated Circuits Conference (CICC), Boston, MA, USA, 2020, pp. 1-4, doi: 10.1109/CICC48029.2020.9075905.

[IEEE Link](https://ieeexplore.ieee.org/document/9075905) \

## Keypoints
- digital error feedback
  - shape the truncation error
  - all in digital domain
  - extend interstage gain error tolerance
- passive quantization error shaping
  - reduce the ratio comparator
  - passive residual gain 2x
  - interstage gain 32x
    - dynamic amplifier 4x
    - reference scaling 8x

## Background
- increase accuracy of the interstage gain
  - minimization
    - closed loop OTA: high power, unfriendly to scaling
    - CDS, CLS: extra clock phase, reduce settling time
    - digital amplifier: require low noise/offset comparator
  - correction
    - foreground calibration: interrupt normal operation
    - background calibration: constrain on the input signal, long converge time
    - interstage gain error shaping (GES): limited error tolerance due to truncation error
- prior GES scheme
  - principle
    - substract quantized Q1_tr before amplifier
    - add it back at the output of the amplifier
    - error is high-pass shaped
  - limits
    - scaling gain from capacitance ratio
    - large mismatch error

## Details
  - digital error feedback, DEF
    - truncates the result of D2 subtracted by the output of Htr(z)
    - the truncation error is also high-pass shaped
    - solely in the digital domain
  - passive noise shaping
    - back-to-back 2 CRES to an voltage gain of 2
      - reduce the ratio of comparator, power and noise
    - 2 CINT to perform passive integration
    - NTF = 1 - 0.75z^-1 by CIN/CRES=3
    - residue amplifier
      - attentues KT/C noise
      - smaller CRES/CINT
  - 2-stage pipelined SAR ADC
    - 7+6 (2b redundancy)
    - G=32
      - 4x dynamic amplifier
      - 8x reference scaling
    - 2nd-order GES
    - GES DAC is 1/16 SAR DAC1

![proposed GES+DEF](https://api2.mubu.com/v3/document_image/f9e18c58-7e88-472f-97cd-3c10d3c131f1-216525.jpg) \

![proposed noise shaping](https://api2.mubu.com/v3/document_image/7dc6f02d-b38e-4060-81a2-b2480e7c5f24-216525.jpg) \

## Conclusion
  - **TECH** 40 nm \
  - **RES** 11-bit \
  - **SAMPLING RATE** 100MS/s \
  - **BW** 6.25 MHz \
  - **POWER** 1.38 mW@1.0V \
  - **SNDR** 77.1 dB \
  - **FOM_S** 173.7 \

## ortant Reference
> *correlated double sampling, CDS*
>
> - [1] K. Nagaraj et al., “Switched-capacitor circuits with reduced sensitivity to amplifier gain,” IEEE Transactions on Circuits and Systems, vol. 34, 50 no. 5, pp. 571–574, May 1987. \
>
> *correlated level shifting, CLS*
>
> - [2] B. R. Gregoire et al., “An Over-60 dB True Rail-to-Rail Performance Using Correlated Level Shifting and an Opamp With Only 30 dB Loop Gain,” IEEE Journal of Solid-State Circuits, vol. 43, no. 12, pp. 2620– 2630, Dec 2008. \
>
> *digital amplifier*
>
> - [3] K. Yoshioka et al., “28.7 A 0.7V 12b 160MS/s 12.8fJ/conv-step pipelined-SAR ADC in 28nm CMOS with digital amplifier technique,” in 2017 IEEE International Solid-State Circuits Conference (ISSCC), Feb 2017, pp. 478–479. \
>
> *foreground calibration*
>
> - [4] D.-Y. Chang et al., “Radix-based digital calibration techniques for multistage recycling pipelined ADCs,” IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 51, no. 11, pp. 2133–2140, Nov 2004. \
>
> *background calibration*
>
> - [5] Y. Zhou et al., “A 12 bit 160 MS/s Two-Step SAR ADC With Background Bit-Weight Calibration Using a Time-Domain Proximity Detector,” IEEE Journal of Solid-State Circuits, vol. 50, no. 4, pp. 920– 931, April 2015. \
>
> *interstage gain error shaping (GES)*
>
> - [6]C.-K. Hsu et al., “A 75.8dB-SNDR Pipeline SAR ADC with 2nd-order Interstage Gain Error Shaping,” in 2019 Symposium on VLSI Circuits, June 2019, pp. C68–C69. \