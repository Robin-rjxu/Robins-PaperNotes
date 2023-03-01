---
title: >-
  ISSCC-2023 A Single-Channel 10GS/s 8b >36.4dB SNDR Time-Domain ADC Featuring
  Loop-Unrolled Asynchronous Successive Approximation in 28nm CMOS
toc: true
tags:
  - ISSCC
  - 2023
  - NTU
  - ADC
abbrlink: 41057
date: 2023-03-01 23:20:43
---

![Keypoints](https://api2.mubu.com/v3/document_image/c9662c06-49b9-448f-9617-da83b7099594-216525.jpg) \

##### Full Citation

Qian Chen, et al, "**A Single-Channel 10GS/s 8b >36.4dB SNDR Time-Domain ADC Featuring Loop-Unrolled Asynchronous Successive Approximation in 28nm CMOS**,"

## Keypoints

- (asynchronous) ASA TDC
  - feedback DAC
    provides async clock
  - register and next comparison
  - enables binary search
  - loop-unrolled
    independent for each cycle
  - intrinsic sync output bits
- V-to-T
  - fast step to set the initial voltage
  - slow constant slope generate time difference
  - sample and distribution to attenuate input voltage
  - keep SNR and not sensitive to jitter
- LMS ref delay tuning to compensate VTC NL
  - vernier delay line for sub-gate delay Tres (400 fs)
  - TDC works as a closed-loop to calibrate ref delay

## Background

- time-domain ADC (TD-ADC)
  - high speed
  - energy and area efficient
- limits
  - trade-off between range and conversion time
    - number of bits
    - cmp metastability and offset
  - long waiting time for multi-bit decisions
  - VTC
    - provide gain from V-to-T conversion
    - suffers from linearity degradation

<img src="https://api2.mubu.com/v3/document_image/d4820a4f-74f6-425a-ab63-7bb7c81df481-216525.jpg" width = "500" alt="Architecture and circuit blocks of the TD-ADC and timing diagram of
the asynchronous SA" align=center />

## Conclusion

**TECH**  28 nm \
**RES**  8-bit \
**SAMPLING RATE**  10 GS/s \
**POWER**  31.7 mW@0.9V \
**DNL** -0.81 LSB \
**INL** +0.74 LSB \
**SFDR** 51.7 dB \
**SNDR** 36.4 dB \
**FOM_W** 58 fJ/conv.-step \

## Important References

> *long waiting time of the time-domain ADC* \
> [1] J. Liu, M. Hassanpourghadi, M.-S. Chen, “A 10GS/s 8b 25fJ/conv.-steep 2850um2 two-step time-domain ADC using delay-tracking pipelined-SAR TDC with 500fs time step in 14nm CMOS technology,” ISSCC, pp. 160-161, Feb. 2022. \
> [2] M. Zhang et al., “a 4× interleaved 10GS/s 8b time-domain ADC with 16× interpolation-based inter-stage gain achieving> 37.5 dB SNDR at 18GHz input,” ISSCC, pp. 252-253, Feb. 2020. \
> [3] S. Zhu et al., “A 2-GS/s 8-bit non-interleaved time-domain flash ADC based on remainder number system in 65-nm CMOS,” IEEE JSSC, vol. 53, no. 4, pp. 288-297, Dec. 2017. \
> 
> *linearity limitation* \
> [4] S. Zhu et al., “A skew-free 10 GS/s 6-bit CMOS ADC with compact time-domain signal folding and inherent DEM.,” IEEE JSSC, vol. 51, no. 8, pp. 1785-1796, May 2016.
>
> *asynchronous SAR* \
> [5] S.-W Chen, R.-W Brodersen, “A 6-bit 600-MS/s 5.3-mW Asynchronous ADC in 0.13-um CMOS,” IEEE JSSC, vol. 41, no. 12, pp. 2669-2689, Oct. 2006.
