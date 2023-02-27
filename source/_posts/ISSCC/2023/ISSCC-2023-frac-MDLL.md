---
title: ISSCC-2023 A Fractional-N Digital MDLL with Injection-Error Scrambling and Background Third-Order DTC Delay Equalizer Achieving -67dBc Fractional Spur
toc: true
tags:
  - ISSCC
  - 2023
  - USC
  - MDLL
abbrlink: 54005
date: 2023-02-27 23:54:16
---

![Keypoints](https://api2.mubu.com/v3/document_image/91db2112-1b34-4f2c-bcf8-daefbd151e83-216525.jpg) \

##### Full Citation

Qiaochu Zhang, et al, "**A Fractional-N Digital MDLL with Injection-Error Scrambling and Background Third-Order DTC Delay Equalizer Achieving -67dBc Fractional Spur**,

## Keypoints

- injection-error scrambling
  - break the periodicit
    randomly distributing the delay to 2 DTCs
  - scrambling the injection position
    between the rising and falling edges of the DCO
  - total delay ping-pongs between TDCO×Dfrac or TDCO×(Dfrac±0.5)
- DTC cali
  - offset, gain and NL
    - digital phase skew for offset
    - current source in DTC for gain
    - 3rd-order LMS for NL
  - in time-domain
    - narrow cali range
    - lower noise floor

## Background

- DTC in frac MDLL
  - align inj to RO phase
  - offset, gain, and INL introduce periodic injection error
- frac spur reduction
  - cali DTC error
    - limited by error estimation or correction accuracy
  - randomization
    - limited degree of randomization

<img src="https://api2.mubu.com/v3/document_image/2bbd56c1-f467-4323-89d7-a73d5e573577-216525.jpg" width = "500" alt="Block diagram of the fractional-N MDLL and phase noise improvement using the proposed techniques." align=center />

## Conclusion

**TECH**  65 nm \
**REF**  50 MHz \
**OUT**  1.0 - 1.8 GHz \
**REF SPUR**  -67 dBc \
**FRAC SPUR**  -58 dBc \
**POWER**  13.56 mW \
**RMS JITTER**  800 fs \
**FOM**  -230.6 dB \

## Important References

> *calibrated gain and offset errors* \
> [1] Q. Zhang et al., “A Fractional-N Digital MDLL with Background Two-Point DTC Calibration Achieving -60dBc Fractional Spur,” ISSCC, pp. 410-411, Feb. 2021. \
> [2] S. Kundu et al., “A Self-Calibrated 1.2-to-3.8GHz 0.0052mm2 Synthesized Fractional-N MDLL Using a 2b Time-Period Comparator in 22nm FinFET CMOS,” ISSCC, pp.388-389, Feb. 2020.
>
> *corrected INL* \
> [3] G. Marucci et al., “A 1.7GHz MDLL-Based Fractional-N Frequency Synthesizer with 1.4ps RMS Integrated Jitter and 3mW Power Using a 1b TDC,” ISSCC, pp. 360-361, Feb. 2014.
>
> *nonuniform injection skip to randomize the DTC INL* \
> [4] Y. He et al., “An Injection-Locked Ring-Oscillator-Based Fractional-N Digital PLL Supporting BLE Frequency Modulation,” IEEE JSSC, vol. 57, no. 6, pp. 1765-1775, June 2022.
