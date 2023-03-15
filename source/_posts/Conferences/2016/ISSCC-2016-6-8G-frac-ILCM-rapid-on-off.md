---
title: >-
  ISSCC-2016 10.6 A 6.75-to-8.25GHz, 250fsrms-integrated-jitter 3.25mW rapid
  on/off PVT-insensitive fractional-N injection-locked clock multiplier in 65nm
  CMOS
toc: true
tags:
  - ISSCC
  - 2016
  - UIUC
  - ILCM
abbrlink: 21316
date: 2023-03-15 23:09:37
---

![Keypoints](https://api2.mubu.com/v3/document_image/ceb3791b-2424-46b0-a3e6-190f0a4444dd-216525.jpg) \

##### Full Citation

A. Elkholy, A. Elmallah, M. Elzeftawi, K. Chang and P. K. Hanumolu, "**10.6 A 6.75-to-8.25GHz, 250fsrms-integrated-jitter 3.25mW rapid on/off PVT-insensitive fractional-N injection-locked clock multiplier in 65nm CMOS**," 2016 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2016, pp. 192-193, doi: 10.1109/ISSCC.2016.7417972.

[IEEE Link](https://ieeexplore.ieee.org/document/7417972) \

## Keypoints

- frac-N ILCM
  - DCDL in the inj path to cancel QE phase
    - 20b FCW_F is truncated to 10b by 2-step DSM
      EFB DSM
    - delay gain is calibrated by the LMS in bg with 1b BBPD
  - integer cycle can obviate the need of infinite phase shift
    coincide with the need the zero-crossing injection
  - pulse gating FTL
    DSM-I shapes DCO QE and suppress spurs
- circuits
  - DTC
    - 8 CMOS  stages loaded by a 7b MOM cap bank
    - 2nd-order ==> 2Tosc ==> 350 ps
  - rapid on/off
    - stored DCO code during off
    - DCO is kick-started by a sync power-on pulse
    - path offset is align by a DCDL

## Background

- ILCMs has better suppress for VCO contributed in-band PN
- ILCM has intrinsic integer-N operation 

<img src="https://api2.mubu.com/v3/document_image/8e864822-7acd-4021-b320-62a23d1ae7ad-216525.jpg" width = "500" alt="Block diagram of the proposed rapid on/off fractional-N ILCM" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  125 MHz \
**OUT**  6.75 - 8.25 GHz \
**REF SPUR**  -43 dBc \
**FRAC SPUR**  -44 dBc \
**POWER**  3.25 mW@0.9V \
**RMS JITTER**  250 fs \
**FOM**  -247 dB \

## Important References

> *FTL adjust freq deviation* \
> [1] B. Helal et al., “A low jitter programmable clock multiplier based on a pulse injection-locked oscillator with a highly-digital tuning loop,” IEEE J. Solid-State Circuits, vol. 44, no. 5, pp.1391-1400, May 2009. \
> [2] A. Elkholy et al., “A 6.75-to-8.25GHz 2.25mW 190fsrms integrated-jitter PVT-insensitive injection-locked clock multiplier using all-digital continuous frequency-tracking loop in 65nm CMOS,” ISSCC Dig. Tech. Papers, pp.188-189, Feb. 2015.
> 
> *frac ILCM with rotating the injection across ring oscillator delay stages* \
> [3] P. Park et al., “An all-digital clock generator using a fractionally injection-locked oscillator in 65nm CMOS,” ISSCC Dig. Tech. Papers, pp.336-337, Feb. 2012.
> 
> *DCDL gain calibrated with BBPD* \
> [4] D. Tasca et al., “A 2.9-4.0-GHz fractional-N digital PLL with bang-bang phase detector and 560-fsrms integrated jitter at 4.5-mW power,” ISSCC Dig. Tech. Papers, pp. 88-90, Feb. 2011. \
> [5] G. Marucci et al., “A 1.7GHz MDLL-based fractional-N frequency synthesizer with 1.4ps RMS integrated jitter and 3mW power using a 1b TDC,” ISSCC Dig. Tech. Papers, pp. 360-361, Feb. 2014.
> 
> *rapid-on* \
> [6] T. Anand et al., “A 7Gb/s rapid on/off embedded-clock serial-link transceiver with 20ns power-on time, 740μW off-state power for energy-proportional links in 65nm CMOS,” ISSCC Dig. Tech. Papers, pp. 64-65, Feb. 2015.
