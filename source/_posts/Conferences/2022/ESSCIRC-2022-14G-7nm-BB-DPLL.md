---
title: >-
  ESSCIRC-2022 A Bang-Bang Digital PLL Covering 11.1-14.3 GHz and 14.7-18.7 GHz
  with sub-40 fs RMS Jitter in 7 nm FinFET Technology
toc: true
tags:
  - ESSCIRC
  - 2022
  - Ericsson
  - PLL
  - BBPD
abbrlink: 60534
date: 2023-03-04 21:09:01
---

![Keypoints](https://api2.mubu.com/v3/document_image/977b3e50-2a11-410e-92d1-90391dac8f6d-216525.jpg) \

##### Full Citation

S. Ek et al., "**A Bang-Bang Digital PLL Covering 11.1-14.3 GHz and 14.7-18.7 GHz with sub-40 fs RMS Jitter in 7 nm FinFET Technology**," ESSCIRC 2022- IEEE 48th European Solid State Circuits Conference (ESSCIRC), Milan, Italy, 2022, pp. 237-240, doi: 10.1109/ESSCIRC55480.2022.9911298.

[IEEE Link](https://ieeexplore.ieee.org/document/9911298) \

## Keypoints

- optimize other noise to well below the ref noise
  - digitize the PN early by BBPD
  - minimize transport delay
  - no pipeline registers in the data path
- loop gain calibration
  - uncertain BBPD jitter and gain
  - firstly, Kp search towards BBPD output slightly above 0
  - then, Ki adjustment to achieve 0-mean BBPD output
- circuits
  - DCO
    - initial freq cali and amp cali
    - dual-core 8-shaped ind
    - coarse bank with MoM Caps (3 thermo MSBs + 4 bin LSBs)
    - 128 level fine tuning with row and col decoders
  - div and BBPD
    - 2-stage by-2 prescaler with maximized slew rate
    - BBPD : CML logic and self-resetting
  - DSP
    - prop + intg type-II 2nd-order PLL
    - 2nd-order DSM @ 1/8 output frequency
    - FSM for multiple functions

## Background

- analog loop filter :poor phase tracking over temperature and tuning making
- narrow BW
  - good for lower ref PN
  - but needs much higher power to achieve better VCO PN
  - design approach balance ref/vco PN ==> optimize other noise below ref PN
- digital PLL
  - limited by  extra QN and nonlinearities
  - reduce design effort
  - faster time-to-marker
    - allow technology migration
    - digitize the phase error earlier
    - BBPD suffice quantize lower PLL RMS jitter

<img src="https://api2.mubu.com/v3/document_image/bb3024b0-6b54-4c68-a121-a8a361e160f6-216525.jpg" width = "500" alt="Bang-Band DPLL architecture" align=center />

## Conclusion

**TECH**  7 nm \
**REF**  491.52 MHz \
**OUT**  11.1 - 18.7 GHz \
**REF SPUR**  -54 dBc \
**POWER**  85.4 mW  \
**RMS JITTER**  37.8 fs \
**FOM**  -249.1 dB \

## Important References

> *analog achieves excellent RMS jitter* \
> [3] Y. Zhao and B. Razavi, “A 19-GHz PLL with 20.3-fs Jitter,” in 2021 Symposium on VLSI Circuits, 2021. \
> [4] D. Turker et al., “A 7.4-to-14GHz PLL with 54fs rms jitter in 16nm Fin-FET for integrated RF-data-converter SoCs,” in 2018 IEEE International Solid - State Circuits Conference - (ISSCC), 2018, pp. 378–380.
> 
> *lower transport delay for better PN* \
> [5] M. Zanuso et al., “Noise Analysis and Minimization in Bang-Bang Digital PLLs,” IEEE Transactions on Circuits and Systems II: Express Briefs, vol. 56, no. 11, pp. 835–839, 2009. \
> [6] D. Pfaff et al., “A 14-GHz Bang-Bang Digital PLL with sub-150fs Integrated Jitter for Wireline Applications in 7nm FinFET,” in 2019 IEEE Custom Integrated Circuits Conference (CICC), vol. 55, no. 3, 2020, pp. 580–591. \
> (look-ahead loop filter)
> 
> *initial freq calibration* \
> [7] P. Andreani et al., “A TX VCO for WCDMA/EDGE in 90 nm RF CMOS,” IEEE Journal of Solid-State Circuits, vol. 46, no. 7, pp. 1618–1626, 2011.
> 
> *input-dependent BBPD jitter* \
> [8] N.D. Dalt, “Markov Chains-Based Derivation of the Phase Detector Gain in Bang-Bang PLLs,” IEEE Transactions on Circuits and Systems II: Express Briefs, vol. 53, no. 11, pp. 1195–1199, 2006.
> 
> *loop gain calibration* \
> [9] S. Jang et al., “An Optimum Loop Gain Tracking All-Digital PLL Using Autocorrelation of Bang–Bang Phase-Frequency Detection,” IEEE Transactions on Circuits and Systems II: Express Briefs, vol. 62, no. 9, pp. 836–840, 2015.
