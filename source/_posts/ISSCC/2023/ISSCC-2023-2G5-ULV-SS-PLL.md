---
title: >-
  ISSCC-2023 A 0.4V-VDD 2.25-to-2.75GHz ULV-SS-PLL Achieving 236.6fsrms Jitter,
  -253.8dB Jitter-Power FoM, and -76.1dBc Reference Spur
toc: true
tags:
  - ISSCC
  - 2023
  - IS-CAS
  - PLL
abbrlink: 60773
date: 2023-02-26 16:58:01
---

![Keypoints](https://api2.mubu.com/v3/document_image/6da94338-3dfa-41a2-837f-5fa0a323662b-216525.jpg) \

##### Full Citation

Zhao Zhang, et al, "**A 0.4V-VDD 2.25-to-2.75GHz ULV-SS-PLL Achieving 236.6fsrms Jitter, -253.8dB Jitter-Power FoM, and -76.1dBc Reference Spur**,"

## Keypoints

- triple-loop SS-PLL
  - P-path direct sampling voltage without gm
  - split varactors for I-path and voltage doubler (VD)-path
    - conv. V2I I-path
    - VD-path with wide FTR in the FLL
- circuits
  - ULV-SSPD : nested high-level boosted buffer (N-HBBUF) reduces on-res of SW
  - ISO-BUF : RC-filter based, low-power, suppress mismatch
  - large swing class-D VCO
    - voltage doubler for the Cvar
    - peak detector provides high Vdd for divider and logic

## Background

- ULP-PLL
  - ADPLL : limited resolution  TDC
  - CP-PLL : poor in-band PN and current mismatch
  - XOR-PLL : type-I and poor spur
  - SS-PLL : good PN but hard for lower than 0.4V
    - limited tuning range of the VCO
    - limited headroom for the ISO-BUF
    - increase on-res of the SW

<img src="https://api2.mubu.com/v3/document_image/96c35502-8946-4e84-ae6e-44a89cabc1de-216525.jpg" width = "700" alt="The proposed ULV-SSPLL" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  62.5 MHz \
**OUT**  2.25 - 2.75 GHz \
**REF SPUR**  -76.1 dBc \
**POWER**  1.03 mW @ 0.4 V \
**RMS JITTER**  236.6 fs \
**FOM**  -253.8 dB \

## Important References

> *ULP PLL* \
> => ADPLL \
> [1] N. Pourmousavian et al., “A 0.5-V 1.6-mW 2.4-GHz Fractional-N All-Digital PLL for Bluetooth LE with PVT-Insensitive TDC Using Switched-Capacitor Doubler in 28-nm CMOS”, IEEE JSSC, vol. 53, no. 9, pp. 2572-2583, Sept. 2018.
>
> => CP-PLL \
> [2] H. Kooshkaki and P. Mercier, “A 0.55mW Fractional-N PLL with a DC-DC Powered Class-D VCO Achieving Better than -66dBc Fractional and Reference Spurs for NB-IoT”, IEEE CICC, pp. 1-4, Mar. 2020.
>
> => XOR-based PD \
> [3] S. Yang et al., “A 0.2-V Energy-Harvesting BLE Transmitter with a Micropower Manager Achieving 25% System Efficiency at 0-dBm Output and 5.2-nW Sleep Power in 28-nm CMOS”, IEEE JSSC, vol. 54, no. 5, pp. 1351-1362, May 2019.
>
> *isolated SSPD* \
> [6] Z. Yang et al., “A 25.4-to-29.5GHz 10.2mW Isolated Sub-Sampling PLL Achieving -252.9dB Jitter-Power FoM and -63dBc Reference Spur”, ISSCC, pp. 270-271, Feb. 2019
