---
title: >-
  CICC-2020 A 0.55mW Fractional-N PLL with a DC-DC Powered Class-D VCO Achieving
  Better than -66dBc Fractional and Reference Spurs for NB-IoT
toc: true
tags:
  - PLL
  - DCDC
  - CICC
  - 2020
  - UCSD
abbrlink: 48962
date: 2020-12-31 13:30:32
---

![Keypoints](https://api2.mubu.com/v3/document_image/dc00fe77-6752-4d06-9405-6926853fe738-216525.jpg) \

##### Full Citation

H. R. Kooshkaki and P. P. Mercier, "**A 0.55mW Fractional-N PLL with a DC-DC Powered Class-D VCO Achieving Better than -66dBc Fractional and Reference Spurs for NB-IoT**," 2020 IEEE Custom Integrated Circuits Conference (CICC), Boston, MA, USA, 2020, pp. 1-4, doi: 10.1109/CICC48029.2020.9075944.
[IEEE Link](https://ieeexplore.ieee.org/document/9075944) \

## Keypoints

  - low power
    - class-D oscillator with a resistive header @0.22 V
    - swcap DC-DC converter (0.55 → 0.22 V)
  - low spurious
    - use reference frequency for DC-DC switching
    - 4-phase interleaving
    - large off-chip decoupling capacitor

## Background

  - NB-IoT
    - congested bands
      - proximal GSM and LTE
      - larger blocker power
    - require minimal spurious to avoid reciprocal mixing
      - primarily arising due to DTC/TDC nonlinearity
  - power supply for PLL
    - low supply voltage for the DCO
    - LDO: good for ripple, but large voltage headroom
    - DC-DC: high efficiency, but large ripple for spur content

## Details

  - low power/spur design
    - class-D VCO
      - 3 VDD output swing
      - head resistor 15Ω
        - increase common-mode tank impedance at 2fLO
        - small area comparing with inductive resonant
        - reduce power
        - improve noise
    - swcap DC-DC converter
      - use reference frequency for DC-DC switching
      - 4-phase interleaving
      - large off-chip decoupling capacitor
  - loop design
    - small bandwidth
    - 8b cap bank to cover bands
    - 7b parallel cap bank in series with the varactor
      - conteract the parallel bank by increasing KVCO
      - reduce settling time
      - constant phase margin

![block diagram](https://api2.mubu.com/v3/document_image/15fad2dd-f88c-4236-882d-3f447a9b5c0d-216525.jpg) \

## Conclusion

  - **TECH** 65nm \
  - **REF** 6MHz \
  - **OUT** 729~960 MHz \
  - **REF SPUR** -67.5 dBc \
  - **FRAC SPUR** -66.3 dBc \
  - **POWER 0.55** mW @ 0.55 V \
  - **RMS JITTER** 6 ps \
  - **FOM** -227 dB \

## Important Reference
>*NB-IoT requirements*
> 
>- [1] Evolved Universal Terrestrial Radio Access (E-UTRA); NB-IOT; Technical Report for BS and EU Radio Transmission and Reception (Release 13), document TS 36.802, 3GPP. \
> 
>*class-D VCO*
> 
>- [5] L. Fanori and P. Andreani, "Class-D CMOS Oscillators," in IEEE Journal of Solid-State Circuits, vol. 48, no. 12, pp. 3105-3119, Dec. 2013. \
> 
>*head impedance*
> 
>- [7] E. Hegazi, H. Sjoland and A. A. Abidi, "A filtering technique to lower LC oscillator phase noise," in IEEE Journal of Solid-State Circuits, vol. 36, no. 12, pp. 1921-1930, Dec. 2001. \
