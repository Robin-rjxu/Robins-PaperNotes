---
title: >-
  ASSCC-2023 A 12.75-to-16-GHz Spur-Jitter-Joint-Optimization SS-PLL Achieving
  -94.55-dBc Reference Spur, 31.9-fs Integrated Jitter and -260.1-dB FoM
toc: true
abbrlink: 6402
date: 2024-01-02 23:00:46
tags:
  - ASSCC
  - 2023
  - PLL
  - SS
  - class-F
  - IS-CAS
---

![Keypoints](https://api2.mubu.com/v3/document_image/fc25d61f-397c-4177-a0ec-191632372c3c-216525.jpg) \

##### Full Citation

Y. Li et al., "**A 12.75-to-16-GHz Spur-Jitter-Joint-Optimization SS-PLL Achieving -94.55-dBc Reference Spur, 31.9-fs Integrated Jitter and -260.1-dB FoM**," 2023 IEEE Asian Solid-State Circuits Conference (A-SSCC), Haikou, China, 2023, pp. 1-3, doi: 10.1109/A-SSCC58667.2023.10347983. \

[IEEE Link](https://ieeexplore.ieee.org/document/10347983) \

## Keypoints

- improve isolation of the SS-PD
  - small-size common-drain transistor
  - regulated narrow pulse generator (R-NPG)
    - pulse width is set by current ratio
    - low-noise falling edge independent on delay
- maintain high gain of the SS-PD
  - large-swing class-F VCO : 4x VDD

## Background

- Sub-sampling PLL
  - ultra-low in-band PN due to high PD gain
  - nonidealies degrades ref spurs
    - isolated buffer between VCO and SPD (high-power)
    - (isolated) iSS-PD (lower gain--> PN++)
- iSS-PD
  - trade-off between gain and nonidealies
    - large-size : gain++  and PN-- / ref_spur++
    - small-size : gain--  and PN++ / ref_spur--
  - conventional sampling pulse
    - gate delay
    - PVT sensitive
    - delay dependent noise

<img src="https://api2.mubu.com/v3/document_image/1202e9c2-0c5c-43b1-a1c4-a221e8d6568a-216525.jpg" width = "700" alt="Overall Architecture of the proposed FN-RSPLL" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  125 MHz \
**OUT**  12.75 ~ 16 GHz \
**REF SPUR**  -94.55 dBc \
**POWER**  9.5 mW  \
**RMS JITTER**  31.9 fs \
**FOM**  -260.1 dB \

## Important References

> *Isolated Buffer* \
> [2] X. Gao, et al., "A Low Noise Sub-Sampling PLL in Which Divider Noise is Eliminated and PD/CP Noise is Not Multiplied by N2," IEEE JSSC, vol. 44, no. 12, pp. 3253-3263, Dec. 2009. \
> 
> *Isolated PD* \
> [4] Z. Yang et al., "16.8 A 25.4-to-29.5GHz 10.2mW Isolated Sub- Sampling PLL Achieving -252.9dB Jitter-Power FoM and -63dBc Reference Spur," ISSCC, pp. 270-272, Feb. 2019. \
> [5] D. -G. Lee, et al., "A Sub-mW 2.4-GHz Active-Mixer-Adopted Sub-Sampling PLL Achieving an FoM of −256 dB," IEEE JSSC, vol. 55, no. 6, pp. 1542-1552, Jun. 2020. \
> [7] Z. Yang, et al., "A 3.3-GHz Integer N-Type-II Sub-Sampling PLL Using a BFSK-Suppressed Push–Pull SS-PD and a Fast-Locking FLL Achieving −82.2-dBc REF Spur and −255-dB FOM," IEEE TVLSI, vol. 30, no. 2, pp. 238-242, Feb. 2022. \
