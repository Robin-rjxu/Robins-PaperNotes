---
title: >-
  ISSCC-2022 A 25.8GHz Integer-N PLL With Time-Amplifying Phase-Frequency
  Detector Achieving 60fsrms Jitter, -252.8dB FoMJ, and Robust Lock Acquisition
  Performance
toc: true
abbrlink: 31810
date: 2023-03-20 22:49:12
tags:
---

![Keypoints](https://api2.mubu.com/v3/document_image/990d7103-80f0-4425-98a9-a646dcb08394-216525.jpg) \

##### Full Citation

X. Geng, Y. Tian, Y. Xiao, Z. Ye, Q. Xie and Z. Wang, "**A 25.8GHz Integer-N PLL With Time-Amplifying Phase-Frequency Detector Achieving 60fsrms Jitter, -252.8dB FoMJ, and Robust Lock Acquisition Performance**," 2022 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2022, pp. 388-390, doi: 10.1109/ISSCC42614.2022.9731578.

[IEEE Link](https://ieeexplore.ieee.org/document/9731578) \

## Keypoints

- time-amplifying phase-frequency detector (TAPFD)
  - high phase error detection gain
    - suppress the CP noise
    - without large current
  - convert time to voltage by discharging C
    - small tin: 1/K lower current 
    - large tin: normal current
  - output transistor sizing trade-off
    - large => lower flicker
    - but slow slope, lower gain and higher PN
  - shared Vbias
    - common-mode VN only
    - ignored by the UP/DN differential operation
  - maintain the robust acquisition ability
    - keep correct polarity as a conv. PFD
    - no need of state ctrl as in a DZ-FLL
- TA-PFD PLL
  - transformer-based class-F VCO
  - 3rd-harmonic boosting-and-extraction
    - PN tracking between the fund. and the 3rd
    - freq tripler as a built-in 3rd extractor
    - high-Q fund. LC tank
    - high output swing
  - feedback the fundamental  (1/3) to save div power

## Background

- suppress CP noise with SSPD
  - introduce a virtual freq multiplier
  - limited lock-in range
  - need an aux-FLL
- challenges of high phase-error gain
  - realize high-gain at the zero-crossing point
  - lower the PN from the TAPFD itself

<img src="https://api2.mubu.com/v3/document_image/777727e2-0851-4085-b05d-d88d753a482a-216525.jpg" width = "800" alt="Overall structure of proposed PLL employing a TAPFD and a VCO with a built-in frequency tripler" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  200 MHz \
**OUT**  24 - 28.2 GHz \
**REF SPUR**  -47 dBc \
**POWER**  14.5 mW  \
**RMS JITTER**  60 fs \
**FOM**  -252.8 dB \

## Important References

> *SS-PLL with aux-FLL* \
> [2] Y. Lim et al., “A 170MHz-Lock-In-Range and –253dB-FoMjitter, 12-to-14.5GHz Subsampling PLL with a 150μW Frequency-Disturbance-Correcting Loop Using a Low-Power Unevenly Spaced Edge Generator,” ISSCC, pp. 280-282, Feb. 2020.
> 
> *a time amplifier (TA) can improve the timing resolution of the TDC* \
> [5] H.-J. Kwon et al., “Analysis of an Open-Loop Time Amplifier with a Time Gain Determined by the Ratio of Bias Current,” IEEE TCAS-II, vol. 61, no. 7, pp. 481-485, July 2014. \
> [6] A. Elkholy et al., “A 3.7 mW Low-Noise Wide-Bandwidth 4.5 GHz Digital Fractional-N PLL Using Time Amplifier-Based TDC,” IEEE JSSC, vol. 50, no. 4, pp. 867-881, Apr. 2015
> 
> *3rd-harmonic boosting-and-extraction technique* \
> [7] Z. Zong et al., “A 60 GHz Frequency Generator Based on a 20 GHz Oscillator and an Implicit Multiplier,” IEEE JSSC, vol. 51, no. 5, pp. 1261-1273, May 2016.
