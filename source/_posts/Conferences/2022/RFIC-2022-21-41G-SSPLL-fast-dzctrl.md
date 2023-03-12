---
title: >-
  RFIC-2022 A 21.8-41.6GHz Fast-Locking Sub-Sampling PLL with Dead Zone
  Automatic Controller Achieving 62.7-fs Jitter and −250.3dB FoM
toc: true
tags:
  - RFIC
  - 2022
  - UESTC
  - PLL
abbrlink: 12831
date: 2023-03-11 23:45:03
---

![Keypoints](https://api2.mubu.com/v3/document_image/3c6580ab-7bdf-44bc-a94b-5f2302d8dca4-216525.jpg) \

##### Full Citation

W. Chen et al., "**A 21.8-41.6GHz Fast-Locking Sub-Sampling PLL with Dead Zone Automatic Controller Achieving 62.7-fs Jitter and −250.3dB FoM**," 2022 IEEE Radio Frequency Integrated Circuits Symposium (RFIC), Denver, CO, USA, 2022, pp. 159-162, doi: 10.1109/RFIC54546.2022.9863104.

[IEEE Link](https://ieeexplore.ieee.org/document/9863104) \

## Keypoints

- QSSPD-based DZ automatic controller (DZAC)
  - SSL for close-in phase lock
  - FLL for frequency locking
- quadrature outputs are all sampled
  - 0/180 outputs are used as conv. SSPD
  - 90/270 outputs are compared to ctrl FLL
    - linear SS region : V90<V270 ( I )
      disable DZ and FLL
    - once out of linear region (lost)
      - FLL turns on immediately
      - disable DZ until back to linear region
    - from initial state
      - FLL and DZ are both enabled

## Background

- mmW signal generator with wide tuning range and low phase noise
- short locking time is for future fast vehicles traveling
- SS PLL
  - FLL with DZ to assist frequency acquisition
    - remove DZ to shorten locking time
    - need to compensate delay mismatch between main loop and FLL

<img src="https://api2.mubu.com/v3/document_image/2d5f991a-8406-4571-93cb-aaabf21de5a6-216525.jpg" width = "500" alt="Block diagram of the proposed wideband fast-locking SSPLL
architecture" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  100 MHz \
**OUT**  21.8 - 41.6 GHz \
**REF SPUR**  -46.1 dBc \
**POWER**  23.6 mW  \
**RMS JITTER**  79.1 fs \
**FOM**  -248.3 dB \

## Important References

> *DZ is removed from the FLL to shorten the locking time* \
> [7] C.-W. Hsu, K. Tripurari, S.-A. Yu, and P. R. Kinget, “A sub-sampling-assisted phase-frequency detector for low-noise PLLs with robust operation under supply interference,” IEEE Trans. Circuits Syst. I, Reg. Papers, vol. 62, no. 1, pp. 90–99, Jan. 2015.
> 
> *soft loop switching in [8] reduces the DZ of FLL to shorten the locking time* \
> [8] D. Liao, F. F. Dai, B. Nauta, and E. A. M. Klumperink, “A 2.4-GHz 16-phase sub-sampling fractional-N PLL with robust soft loop switching,” IEEE J. Solid-State Circuits, vol. 53, no. 3, pp. 715–727, Mar. 2018.
> 
> *quad-mode mmW oscillator* \
> [12] Y. Shu, H. J. Qian, and X. Luo, “A 2-D mode-switching quad-core oscillator using E-M mixed-coupling resonance boosting,” IEEE J. Solid-State Circuits, vol. 56, no. 6, pp. 1711–1721, Jun. 2021.
