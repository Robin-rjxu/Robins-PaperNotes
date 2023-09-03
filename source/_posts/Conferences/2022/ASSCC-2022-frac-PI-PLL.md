---
title: >-
  ASSCC-2022 An Attachable Fractional Divider Transforming an Integer-N PLL Into
  a Fractional-N PLL with SSC Capability
toc: true
tags:
  - ASSCC
  - 2022
  - Renesas
  - PLL
  - RO
  - PI
abbrlink: 19998
date: 2023-09-03 22:38:26
---

![Keypoints](https://api2.mubu.com/v3/document_image/2b584bad-64da-4499-8da2-622aa8e58db3-216525.jpg) \

##### Full Citation

A. Motozawa, Y. Hiraku, Y. Hirai, N. Hiyama, Y. Imanaka and F. Morishita, "**An Attachable Fractional Divider Transforming an Integer-N PLL Into a Fractional-N PLL with SSC Capability**," 2022 IEEE Asian Solid-State Circuits Conference (A-SSCC), Taipei, Taiwan, 2022, pp. 1-3, doi: 10.1109/A-SSCC56115.2022.9980697.

[IEEE Link](https://ieeexplore.ieee.org/document/9980697) \

## Keypoints

- transform an Int-N PLL into a Frac-N PLL with a frac-DIV to generate FB signal
  - reduce operating frequency by DIV2+DIV8
  - INT code generates EN window (INT_coarse)
  - EN intermitted signal selects PI input signals (INT_fine)
  - PI deals with EDG1 and EDG2 with 1Tvco interval
- improve PI linearity by auto-region-keeping (ARK)
  - CMOS PI controls voltage slope by current DACs (2b coarse+3b fine)
  - a feedback path to ensure nMOS IN saturation region

## Background

- use fractional divider to make a int-N PLL to a frac-N PLL
  - fast migration from existing design
  - less design complexity in analog phase detection(TDC/DTC)
  - no need of extra digital calibration
- transform an Int-N PLL into a Frac-N PLL with a frac-DIV to generate FB
  - need extra frequency information
  - not common for every PLLs

<img src="https://api2.mubu.com/v3/document_image/a948cf8e-1fb7-461e-86d1-d2ad1fc33f17-216525.jpg" width = "600" alt="Circuit diagram of the proposed PI and its waveform" align=center />

## Conclusion

**TECH**  12 nm \
**REF**  30 MHz \
**OUT**  1.5-4.2 GHz \
**FRAC SPUR**  -69.3 dBc \
**POWER**  3.2 mW  \
**RMS JITTER**  5.99 ps \
**FOM**  -229.5 dB \

## Important References

> *extra coarse frequency control is needed to generate the frequency information* \
> [3] Tsung-Kai Kao et al., “ A Wideband Fractional-N Ring PLL with Fractional-Spur Suppression Using Spectrally Shaped Segmentation,” ISSCC 2013:416, 417.
> 
> *two-step phase interpolation, one PI is in PD, cannot be widely applied to any PLL* \
> [4] J. Tao et al., “ A 1.6-GHz 3.3-mW 1.5-MHz Wide Bandwidth ∆∑ Fractional-N PLL with a Single Path FIR Phase Noise Filtering, “ ASSCC 2018:215-218.
> 
> *one time interval of the output clock is directly interpolated in 5b resolution* \
> [5] T. Saeki et al., “ A 1.3-cycle lock time, non-PLL/DLL clock multiplier based on direct clock cycle interpolation for "clock on demand", “ JSSC 2000 Vol.35, No.11, Nov.: 1581-1590.
