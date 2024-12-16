---
title: >-
  VLSI-2023 A Reference-Sampling PLL with Low-Ripple Double-Sampling PD
  Achieving −80-dBc Reference Spur and −259-dB FoM with 12-pF Input Load
toc: true
tags:
  - VLSI
  - 2023
  - SPD
  - RS
  - PLL
  - UTokyo
abbrlink: 46814
date: 2024-12-16 17:12:51
---

![Keypoints](https://api2.mubu.com/v3/document_image/216525_5ad0236b-e442-45c1-97c8-960d81157c6a.png) \

##### Full Citation

Z. Yang, M. Osada, S. Li, Y. Zhu and T. Iizuka, "**A Reference-Sampling PLL with Low-Ripple Double-Sampling PD Achieving −80-dBc Reference Spur and −259-dB FoM with 12-pF Input Load**," 2023 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Kyoto, Japan, 2023, pp. 1-2, doi: 10.23919/VLSITechnologyandCir57934.2023.10185259.

[IEEE Link](https://ieeexplore.ieee.org/document/10185259/) \

## Keypoints

- low-ripple double-sampling phase detector (DSPD)
  - not need DCC
  - directly samples the sinusoidal reference
  - samples reference falling and rising edges
  - double sampling improves 3-dB inband PN
- reduce input load and ref spur
  - unity-gain buffer (UGB) based charger
    - deal with feedthrough from source-drain parasitic
    - UGB-based charger sets the holding CT
  - multiplexed dummy sampler
    - emulate the same bias conditions
    - cancels the complementary charge injections
- reference-sampling PLL (RSPLL)
  - differential DSPD
  - LC voltage-controlled oscillator (VCO)
  - multi-modulus divider (MMD)
  - clock generator
    - MMD output
    - two sets of narrow pulses

## Background

- high-speed communication systems
  - Low-jitter and low-spur PLLs
  - sampling/sub-sampling PLLs (S/SSPLLs)
    - high phase detection gain
    - lower spur, jitter, and power consumption
  - huge reference buffer (RBUF) 
    - low jitter : sub-100fs jitter
    - high-slew-rate clock with low PN
    - worse power efficiency
- reference-sampling PLL (RSPLL)
  - XO’s buffer amplifier
    - consumes an extra power of RBUF
  - directly samples the sine-wave reference
    - eliminates the RBUF power
    - better FoM than RBUF-based SPLL
    - previous work
      - narrow-pulse sampling 
        - T-shape switch
        - one more holding capacitor of CT
        - need a SH-based charger to set CT
      - differential multiplexed sampling paths
        - double input load

<img src="https://api2.mubu.com/v3/document_image/216525_f3e34e60-ccd9-4f42-f130-3c4588e0f5b6.png" width = "500" alt="Overall Architecture of Proposed RSPLL" align=center />

<img src="https://api2.mubu.com/v3/document_image/216525_b5afab7c-9825-45b9-febd-f470e8a88473.png" width = "500" alt="comparison of the Ref SPD" align=center />

<img src="https://api2.mubu.com/v3/document_image/216525_8a7b6956-d601-4df4-f28a-e8edbcc69d3d.png" width = "500" alt="Proposed low-ripple SPD" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  100 MHz \
**OUT**  3.4 ~ 4 GHz \
**REF SPUR**  -80.3 dBc \
**POWER**  3.1 mW  \
**RMS JITTER**  62.9 fs \
**FOM**  -259.1 dB \

## Important References

> *SPLL with excellent FoM* \
> [1] J. Gong, RFIC, 2020. \
> [2] Y. Zhao, VLSI, 2021. (high-power XO buffer amplifier)
> 
> *directly samples the sine-wave reference* \
> [3] Z. Yang, SSCL, 2020. (narrow-pulse sampling and a T-shape switch)
>
> *high-performance PLLs* \
> [4] T. Xu, TCAS-I, 2022. \
> [5] C. Elgaard, ESSCIRC, 2017.