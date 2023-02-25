---
title: >-
  ISSCC-2023 A 47fsrms-Jitter and 26.6mW 103.5GHz PLL with Power-Gating
  Injection-Locked Frequency-Multiplier-Based Phase Detector and Extended Loop
  Bandwidth
toc: true
tags:
  - ISSCC
  - 2023
  - KAIST
  - PLL
abbrlink: 6938
date: 2023-02-25 22:54:01
---

![Keypoints](https://api2.mubu.com/v3/document_image/d3156f23-36a9-4878-93b0-a51bef8954ad-216525.jpg) \

##### Full Citation

Jooeun Bang, et al, "**A 47fsrms-Jitter and 26.6mW 103.5GHz PLL with Power-Gating Injection-Locked Frequency-Multiplier-Based Phase Detector and Extended Loop Bandwidth**,"

## Keypoints

- PG-ILFM PD
  - low PN with mixing (down-conv without gain att)
  - effective PN suppression with periodic phase reset
  - but discontinuous
- PLL with PG-ILFM PF
  - separate prop and intg paths
  - reset switch nulls PD pole
  - larger sampling Cs for lower in-band PN
- details
  - short pulse to PG R-VCO for fast restart
  - frequency offset cancellation to keep high PD gain

## Background

- sub-THz local-oscillator (LO) signals
  - need extremely low jitter
  - extend BW to suppress VCO PN
  - cascaded PLLs : area, power ++
  - subsampling PLL : high PD gain is valid with low fvco < fpole_pd
- PG-ILFM PD
  - low PN, discontinuous
  - mixing with output while keep low PN and high gain
  - BW limited
    - type-II PLL
    - 2nd-order DLF
    - gm-amplifier

<img src="https://api2.mubu.com/v3/document_image/6861c0c7-b524-4c44-a4ee-8e444817d61d-216525.jpg" width = "500" alt="Overall architecture of the proposed sub-THz PLL with PF-ILFM PD" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  500 MHz \
**OUT**  99.5 -  103.5 GHz \
**REF SPUR**  -42 dBc \
**POWER**  26.6 mW  \
**RMS JITTER**  47 fs \
**FOM**  -252.3 dB \

## Important References

> *PG-ILFM PD* \
> [3] S. Yoo et al., “An 82fsrms-Jitter and 22.5mW-Power, 102GHz W-Band PLL Using a Power-Gating Injection-Locked Frequency-Multiplier-Based Phase Detector in 65nm CMOS,” ISSCC, pp. 330-331, Feb. 2021.
> 
> *separate prop and intg paths in a sampling PLL* \
> [4] W. Wu et al., “A 28-nm 75-fsrms Analog Fractional-N Sampling PLL With a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction,” IEEE JSSC, vol. 54, no. 5, pp. 1254-1265, May 2019.
