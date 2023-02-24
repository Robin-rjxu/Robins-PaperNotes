---
title: >-
  ISSCC-2023 A 32kHz-Reference 2.4GHz Fractional-N Nonuniform Oversampling PLL
  with Gain-Boosted PD and Loop-Gain Calibration
toc: true
tags:
  - ISSCC
  - 2023
  - TokyoTech
  - PLL
abbrlink: 58657
date: 2023-02-23 23:23:03
---

![Keypoints](https://api2.mubu.com/v3/document_image/f20f73e4-3ae2-41e8-b2bc-03993702b097-216525.jpg) \

##### Full Citation

Junjun Qiu, et al, "**A 32kHz-Reference 2.4GHz Fractional-N Nonuniform Oversampling PLL with Gain-Boosted PD and Loop-Gain Calibration**,"

## Keypoints

- nonuniform oversampling
  - increase sampling freq near the zero  crossing points
  - null sampling at noisy peaks
- gain boosted phase detector
  - to suppress voltage noise
  - high DAC slope with opposite polarity of the ref
- adaptive loop gain calibration
  - achieve zero auto-corr of PD outputs
  - update LuT in background

## Background

- '1x' sampling PLL has limited 1/10 Fref BW
  - over sampling the sinusoidal ref achieves much higher BW
- ref-oversampling PLL suffers from voltage noise due to slow slope
- PLL jitter depends on the cosine ref slope
  - varying slope
  - difficult to predict and follow the optimum loop gain

<img src="https://api2.mubu.com/v3/document_image/3f1b7f5f-2a5a-4ac0-9a24-d77addd9f9be-216525.jpg" width = "700" alt="Overall architecture of the proposed nonuniform OSPLL" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  32.768 KHz \
**OUT**  2.0-2.8 GHz \
**REF SPUR**  -68 dBc \
**FRAC SPUR**  -43 dBc \
**POWER**  3.8 mW \
**RMS JITTER**  4.95 fs \
**FOM**  -220.3 dB \

## Important References

> *Ref Oversampling PLL* \
> [3] J. Qiu et al., “A 32-kHz-Reference 2.4-GHz Fractional-N Oversampling PLL with 200-kHz Loop Bandwidth,” IEEE JSSC, vol. 56, no. 12, pp. 3741-3755, Dec. 2021.
