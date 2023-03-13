---
title: >-
  RFIC-2022 An 8.2-10.2 GHz Digitally Controlled Oscillator in 28-nm CMOS Using
  Constantly-Conducting NMOS Biased Switchable Capacitor
toc: true
tags:
  - RFIC
  - 2022
  - RWTH-AU
  - DCO
abbrlink: 37985
date: 2023-03-13 19:48:17
---

![Keypoints](https://api2.mubu.com/v3/document_image/bca7aff5-bbca-4303-afe0-9d2432314d7f-216525.jpg) \

##### Full Citation

L. Wang et al., "**An 8.2-10.2 GHz Digitally Controlled Oscillator in 28-nm CMOS Using Constantly-Conducting NMOS Biased Switchable Capacitor**," 2022 IEEE Radio Frequency Integrated Circuits Symposium (RFIC), Denver, CO, USA, 2022, pp. 207-210, doi: 10.1109/RFIC54546.2022.9863152.

[IEEE Link](https://ieeexplore.ieee.org/document/9863152) \

## Keypoints

- contantly-conducting NMOS SC
  - use NMOS pair to form both pull-up/down
  - on-state : source at GND
  - switch-off  : both gate/source to VDD
    - high-ohmic path
    - large q-factor with gate is at VDD
    - small off-state capacitance
  - good transient
    - channel is not switched
    - low parasitic
      - same device type sharing diffusion
      - compact layout
- coarse/intermediate/fine tuning
  - Cmom from PDK for coarse/intermediate
  - additional series C for fine
- circuits
  - regulated supply
  - PMOS switch as tail bias
  - matrix cap array (256, 64, 128)
    - row and col decoder is embedded into cell
    - all are unitary

## Background

- DCO for ADPLL
  - sufficient quality factor
  - large overall capacitance difference between on and off state
  - fine tuning resolution
- conv. DCO
  - binary-weighted capacitor array 
    - non-monotonic tuning from PVT variations
  - capacitor array with unitary cells
    - inherent monotonicity
    - accumulate large off-state capacitance
    - thus limit the oscillator tuning range
  - resistor-biased SC
    - small off-state capacitance
    - due to small number of used MOS devices
    - limited by poly res thus large area
    - large RC time constant and poor transient response
  - CMOS structure of the SC
    - better transient response with pulling-up PMOS
    - large area for lower quality factor
    - off-state capacitance limits tuning range


<img src="https://api2.mubu.com/v3/document_image/7fa3c343-e75c-42c0-8ab8-16e8d677e454-216525.jpg" width = "500" alt="Proposed switchable capacitor structure biased by a constantly conducting NMOS pair. (a) Coarse and intermediate bank unit cell. (b)Schematic of the fine tuning cell and layout of the customized small fringe capacitor" align=center />

## Conclusion

**TECH**  28 nm \
**FOUT**  8.2 - 10.2 GHz (24%) \
**FRES**  17 KHz/bit \
**PN**  -115.1 \
**POWER**  4.5 mW  \
**FOM**  183 dB \

## Important References

> *drastice amplitude variation during switch cap and wrong locking* \
> [1] P. Andreani, K. Kozmin, P. Sandrup, M. Nilsson, and T. Mattsson, “A TX VCO for WCDMA/EDGE in 90 nm RF CMOS,” IEEE Journal of Solid-State Circuits, vol. 46, no. 7, pp. 1618–1626, 2011.
