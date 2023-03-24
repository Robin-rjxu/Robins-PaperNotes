---
title: >-
  ISSCC-2018 A digital frequency synthesizer with dither-assisted pulling
  mitigation for simultaneous DCO and reference path coupling
toc: true
tags:
  - ISSCC
  - 2018
  - USC
  - digital
  - PLL
abbrlink: 24254
date: 2023-03-22 20:25:51
---

![Keypoints](https://api2.mubu.com/v3/document_image/fe3b9ae6-b7d5-4849-ba81-fc0533a20453-216525.jpg) \

##### Full Citation

C. -R. Ho and M. S. -W. Chen, "**A digital frequency synthesizer with dither-assisted pulling mitigation for simultaneous DCO and reference path coupling**," 2018 IEEE International Solid - State Circuits Conference - (ISSCC), San Francisco, CA, USA, 2018, pp. 254-256, doi: 10.1109/ISSCC.2018.8310280.

[IEEE Link](https://ieeexplore.ieee.org/document/8310280) \

## Keypoints

- dither-assisted pulling migration
  - orthogonalizes the coupling from both DCO and rerf paths
  - simultaneous rejection in the background
  - minimizing the hardware overhead
- phase disturbances from DCO and ref are indistinguishable in TDC output
  - dither the delay of the ref path with a PN code
  - randomize ref-coupled disturbance
  - DCO-coupled disturbance remains intact
  - they can be extracted separately via PN correlators
- three key components
  - pseudo-random sequence generator
  - ref-pulling mitigation loop at the DLF input
  - DCO-pulling mitigation loop at the DLF output
- LMS-based migration loops
  depending on pulling signal types
  - external digital I/Q input for PA pulling
  - on-chip DDS for osc mutual pulling

## Background

- Injection pulling on frequency synthesizers
  - aggressor waveform in most cases is known a priori
  - transfer function of the coupling path is unpredictable
- the oscillator of the victim PLL can be disturbed
  - high-power PA
  - other nearby PLLs
- previous adaptive techniques
  - track TFs in the background
  - only focus on pulling mitigation of the oscillator
  - incur high overhead
- pulling paths for osc and ref are different
- phase disturbances from two paths are indistinguishable at the TDC output

<img src="https://api2.mubu.com/v3/document_image/6e89c6ab-2f68-4e8c-8f17-adbc7ce306d5-216525.jpg" width = "800" alt="Digital PLL architecture with the DCO-pulling and reference-pulling mitigation scheme" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  32 MHz \
**OUT**  3.2 GHz \
**REF SPUR**  -55.7 dBc \
**POWER**  21.3 mW  \
**IMPROVEMENT** \
    22.5 dB for DCO mutual \
    12 dB for PA pulling \

## Important References

> *interfering signal also affect reference clock* \
> [1] R. Stazewski, et al., “Spur-Free Multirate All-Digital PLL for Mobile Phones in 65 nm CMOS,” IEEE JSSC, vol. 46, no. 12, pp. 2904-2919, Dec. 2011.
> 
> *adaptive track the transfer function in the background* \
> [1] R. Stazewski, et al., “Spur-Free Multirate All-Digital PLL for Mobile Phones in 65 nm CMOS,” IEEE JSSC, vol. 46, no. 12, pp. 2904-2919, Dec. 2011. \
> [2] A. Mirzaei and H. Darabi, “Pulling Mitigation in Wireless Transmitters,” IEEE JSSC, vol. 49, no. 9, pp. 1958-1970, Sep. 2014. \
> [3] G. Puma and C. Carbonne, “Mitigation of Oscillator Pulling in SoCs,” IEEE JSSC, vol. 51, no. 2, pp. 348-356, Feb. 2016. \
> [4] R. Winoto, et al., “A 2×2 WLAN and Bluetooth Combo SoC in 28nm CMOS with On-Chip WLAN Digital Power Amplifier, Integrated 2G/BT SP3T Switch and BT Pulling Cancelation,” ISSCC, pp. 170-171, Feb. 2016.
> 
> *the oscillator pulling mitigation can worsen perturbation caused by reference path coupling* \
> *calibration-free TDC is injection-locked to the LC-DCO* \
> [5] C.-R. Ho and M. Chen, “Interference-Induced DCO Spur Mitigation for Digital Phase Locked Loop in 65-nm CMOS,” ESSCIRC, pp. 213-216, Sep. 2016. 
