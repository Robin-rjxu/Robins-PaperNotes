---
title: CICC-2019 An HDL-described Fully-synthesizable Sub-GHz IoT Transceiver with Ring Oscillator based Frequency Synthesizer and Digital Background EVM Calibration
toc: true
abbrlink: 28138
date: 2023-03-14 23:53:34
tags:
  - CICC
  - 2019
  - TokyoTech
  - TRX
  - RF
---

![Keypoints](https://api2.mubu.com/v3/document_image/4d1030b9-17c7-40b3-926c-8740d2c79e4a-216525.jpg) \

#### Full Citation

B. Liu et al., "**An HDL-described Fully-synthesizable Sub-GHz IoT Transceiver with Ring Oscillator based Frequency Synthesizer and Digital Background EVM Calibration**," 2019 IEEE Custom Integrated Circuits Conference (CICC), Austin, TX, USA, 2019, pp. 1-4, doi: 10.1109/CICC.2019.8780372.

[IEEE Link](https://ieeexplore.ieee.org/document/8780372) \

## Keypoints

- synthesizable TRX
  - TX
    - digital baseband (DBB)
      - FSK modulator
      - Gaussian pulse-shaping filter
      - interpolation filter chain
    - RO based frac-N IL-PLL with DTC
    - DPA
  - RX
    - analog frontend (AFE)
      - LNTA
      - passive mixer
      - BPF and VGA
        flip-voltage follower (FVF)
    - 10b SAR ADC
    - digital IF stage 
      @ 1MHz
      - quadrature down conversion
      - channel filtering (IIR)
      - timing recovery
      - GMSK demodulation
        one-bit difference demodulation
  - Calibration
    - DTC gain and nonlinearity
    - DCO freq
    - PA output power ctrl

## Background

- analog customized TRX
  - with sufficient margin
  - inelegant and expensive
- digital synthesizable TRX
  - reduce design/test cost
  - improve process portability and scalability
  - flexible TRX configurations for various user scenarios

<img src="https://api2.mubu.com/v3/document_image/d4d4e181-23d6-4456-b8c1-9eb9e0d8aa2f-216525.jpg" width = "500" alt="System diagram of proposed sub-GHz IoT transceiver" align=center />

## Conclusion

**TECH**  65 nm \
**MOD**  GM/FSK \
**FLO**  922 MHz \
**TX POUT**  -30~2 dBm \
**TX EVM**  0.9% \
**TX EFFIENCY**  21.7% \
**RX  DATA RATE**  500 Kbps \
**RX SENSITIVITY**  -94 \

## Important References

> *FSK TX : RO-based sub-integer-N PLL* \
> [5] X. Chen, J. Breiholz, F. Yahya, C. Lukas, H. Kim, B. Calhoun, and D. Wentzloff, “A 486 μW All-Digital Bluetooth Low Energy Transmitter with Ring Oscillator Based ADPLL for IoT applications,” in IEEE RFIC Symp. Dig. Papers, June 2018, pp. 168–171.
> 
> *DTC gain and nonlinearity calibration* \
> [6] B. Liu, H. C. Ngo, K. Nakata, W. Deng, Y. Zhang, J. Qiu,T. Yoshioka, J. Emmei, H. Zhang, J. Pang, A. T. Narayanan, D. Yang, H. Liu, K. Okada, and A. Matsuzawa, “A 1.2ps-jitter fully-synthesizable fully-calibrated fractional-N injection-locked PLL using True Arbitrary Nonlinearity Calibration technique,” in Proc. IEEE CICC, Apr. 2018, pp. 1–4
