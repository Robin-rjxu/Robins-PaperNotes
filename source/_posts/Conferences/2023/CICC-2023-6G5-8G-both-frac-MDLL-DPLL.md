---
title: CICC-2023-6G5-8G-both-frac-MDLL-DPLL
toc: true
tags:
  - CICC
  - 2023
  - TokyoTech
  - PLL
abbrlink: 50381
date: 2023-05-31 23:49:27
---

![Keypoints](https://api2.mubu.com/v3/document_image/0ea13867-de2a-4c79-8b7e-cdd8f779e2d7-216525.jpg) \

##### Full Citation

D. Xu et al., "**A 6.5-to-8GHz Cascaded Dual-Fractional-N Digital PLL Achieving -63.7dBc Fractional Spurs with 50MHz Reference**," 2023 IEEE Custom Integrated Circuits Conference (CICC), San Antonio, TX, USA, 2023, pp. 1-2, doi: 10.1109/CICC57935.2023.10121180.

![IEEE Link](https://ieeexplore.ieee.org/document/10121180) \

## Keypoints

- dual-fractional-N digital PLL
  - large fractional frequency control words (FCWs)
  - push the offset frequencies of spurs beyond the BW
  - 1st-stage: RO-based MDLL (1.2~1.5G, div-by-4 for the 2nd stage)
  - 2nd-stage: type-II BB LC-DPLL(6.5-8G)
    - low-BW to filter RO PN of the 1st stage
    - BBPD
    - FLL at input/8 (< 50MHz)
- two DTC has the same effect on the final output spurs
  - 1st-stage: 14b segmented VS-DTC (4b coarse + 10b fine)
    - 0.2ps resolution
    - piecewise-linear (PWL) INL cali (0.05% INL)
    - PN is 14dB lower than CS-DTC
  - 2nd-stage: 10b 0.3ps-res VSDTC
- DCO 
  - high-Q single-turn tank inductor
  - 8-shape inductor as the tail filter for better isolation

## Background

- cascaded-PLL
  - limited frequency resolution
- CS-DTC 
  - better linearity
  - DAC needs voltage headroom for constant bias current
  - large delay offset (tofst) 
  - worse PN

<img src="https://api2.mubu.com/v3/document_image/96aa3c33-9951-4d2d-99d7-e17c1febba0f-216525.jpg" width = "700" alt="Overall architecture of proposed cascaded dual-fractional-N digital PLL" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  50 MHz \
**OUT**  6.5 ~ 8 GHz \
**REF SPUR**  -72.4 dBc \
**FRAC SPUR**  -63.7 dBc \
**POWER**  14.2 mW  \
**RMS JITTER**  191 fs \
**FOM**  -242.91 dB \

## Important References

> *Cascaded PLLs* \
> [1] T. Tsai et al., “A Cascaded PLL (LC-PLL + RO-PLL) with a Programmable Double Realignment Achieving 204fs Integrated Jitter (100kHz to 100MHz) and -72dB Reference Spur,” ISSCC, Feb.2022.
> 
> *1st-stage fractional-N PLL and a 2nd-stage integer-N PLL* \
> [2] W. El-Halwagy et al., "A 28-GHz Quadrature Fractional-N Frequency Synthesizer for 5G Transceivers with Less Than 100-fs Jitter Based on Cascaded PLL Architecture," TMTT, Feb. 2017.
> 
> *1st-stage integer-N PLL and a 2nd-stage fractional-N PLL* \
> [3] L. Kong et al., " A 2.4-GHz 6.4-mW Fractional-N Inductorless RF Synthesizer," JSSC, Aug. 2017.
> 
> *DTC PWL NL cali* \
> [4] B. Liu et al., " A Fully Synthesizable Fractional-N MDLL With Zero-Order Interpolation-Based DTC Nonlinearity Calibration and Two-Step Hybrid Phase Offset Calibration," TCAS-I, Feb. 2021.

