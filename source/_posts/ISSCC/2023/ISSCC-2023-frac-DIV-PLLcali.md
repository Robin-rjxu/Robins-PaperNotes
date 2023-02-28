---
title: >-
  ISSCC-2023 A 10-to-300MHz Fractional Output Divider with -80dB Worst-Case
  Fractional Spurs Using Auxiliary-PLL-Based Background 0th/1st/2nd-Order DTC
  INL Calibration
toc: true
tags:
  - ISSCC
  - 2023
  - TsinghuaU
  - DIV
  - DTC
abbrlink: 19033
date: 2023-03-01 00:01:07
---

![Keypoints](https://api2.mubu.com/v3/document_image/c28e5fb2-d23a-4a86-a006-2a4b209073d2-216525.jpg) \

##### Full Citation

Yumeng Yang, et al, "**A 10-to-300MHz Fractional Output Divider with -80dB Worst-Case Fractional Spurs Using Auxiliary-PLL-Based Background 0th/1st/2nd-Order DTC INL Calibration**,"

## Keypoints

- fractional output divider (FOD)
  - aux-PLL-based
    - PLL follows FOD static phase
      functions as a frequency domain filter
    - BBPD extracts phase error contributes to spurs
      PLL accumulates the spur components
  - 0th/1st/2nd-order DTC-INL cali
    - piecewise cali with LuT
    - 16b predistortion

## Background

- DTC-based fractional output divider for independent output
- DTC is PVT sensitive (gain mismatch/INL ==> large spurs)
  - closed-loop cali is used widely in PLLs
  - open-loop cali : cannot deal with NL
    - complementary-replica DTC for gain cali
      power, area, and introduce extra mismatch
    - cali only when overflows
      less effective and slow convergence
    - pattern extraction based
      need prior knowledge and complex

<img src="https://api2.mubu.com/v3/document_image/fc551d61-580c-4ecf-8465-708ba9a20c44-216525.jpg" width = "500" alt="Overall architecture of the proposed FOD with the INL calibration based on the aux-PLL" align=center />

## Conclusion

**TECH**  28 nm \
**FREQ IN** 8 GHz \
**FREQ OUT**  10 - 300 MHz \
**FRAC SPUR**  -85 dBc \
**POWER**  1.25 mW \
**RMS JITTER**  316 fs \

## Important References

> *complementary-replica DTC* \
> [1] A. Elkholy et al., “Low-Jitter Multi-Output All-Digital Clock Generator Using DTC-Based Open Loop Fractional Dividers,” IEEE JSSC, vol. 53, no. 6, pp. 1806-1817, June 2018.
> 
> *cali when overflow* \
> [2] C.-Y. Lin et al., “A 0.008mm2 1.5mW 0.625-to-200MHz Fractional Output Divider with 120fsrms Jitter Based on Replica-DTC-Free Background Calibration,” ISSCC, pp. 412-413, Feb. 2021.
> 
> *Extracting a periodic pattern* \
> [3] S.-Y. Hung and S. Pamarti, “A 0.5-to-2.5GHz Multi-Output Fractional Frequency Synthesizer with 90fs Jitter and -106dBc Spurious Tones Based on Digital Spur Cancellation,” ISSCC, pp. 262-263, Feb. 2019.
