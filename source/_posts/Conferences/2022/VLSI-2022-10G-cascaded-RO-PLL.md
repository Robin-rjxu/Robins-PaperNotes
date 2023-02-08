---
title: >-
  VLSI-2022 A 10-GHz Inductorless Cascaded PLL with Zero-ISF Subsampling Phase
  Detector Achieving −63-dBc Reference Spur, 175-fs RMS Jitter and −240-dB
  FOMjitter
toc: true
tags:
  - VLSI
  - 2022
  - PLL
  - RO
  - TokyoU
abbrlink: 46608
date: 2023-02-08 21:33:32
---

![Keypoints](https://api2.mubu.com/v3/document_image/3a176998-561d-4699-b2b6-ce6d6d61c373-216525.jpg) \

##### Full Citation

Z. Yang, Z. Xu, M. Osada and T. Iizuka, "**A 10-GHz Inductorless Cascaded PLL with Zero-ISF Subsampling Phase Detector Achieving −63-dBc Reference Spur, 175-fs RMS Jitter and −240-dB FOMjitter**," 2022 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2022, pp. 10-11, doi: 10.1109/VLSITechnologyandCir46769.2022.9830382.

[IEEE Link](https://ieeexplore.ieee.org/document/9830382) \

## Keypoints

- inductor-less cascaded PLL
  RO for both stages
  - cascased 2 stages
  - single-stage SH as SSPD for prop path
    - track the input within the zero-ISF region
    - unnecessity of a conventional RC filter
    - remove extra pole
      - lower PN peak
      - allow wide BW
  - track voltage at zero-ISF
    - load varactor by a single cell
    - feedback by another cell
    - timing marge: 100~200 ps
  - split prop and intg paths

## Background

- drastic PN degradation of RO for above 5 GHz
- 2nd-stage SSPD
  - lower ref spur
  - loop BW limited
  - higher PN peak (type-II, reduced PM)

![Proposed Zero-ISF SPD and the Cascased PLL](https://api2.mubu.com/v3/document_image/c424c892-72f9-477f-b9f9-6ce520f9b52f-216525.jpg)

## Conclusion

**TECH** 65nm \
**REF** 120MHz \
**OUT** 10 GHz \
**REF SPUR**  -63 dBc \
**POWER**  30.82 mW \
**RMS JITTER** 175.3 fs \
**FOM** -240.21 dB \

