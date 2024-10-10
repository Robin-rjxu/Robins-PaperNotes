---
title: ISSCC-2024-7G-BB-DPLL-cascaded-frac-div-pseudo-diff-dtc
toc: true
tags:
  - ISSCC
  - 2024
  - DPLL
  - BBPD
  - DTC
  - TokyoTech
abbrlink: 50501
date: 2024-10-10 21:14:09
---

![Keypoints](https://s21.ax1x.com/2024/10/10/pAJHrBq.png) \

##### Full Citation

D. Xu et al., "**10.3 A 7GHz Digital PLL with Cascaded Fractional Divider and Pseudo-Differential DTC Achieving -62.1dBc Fractional Spur and 143.7fs Integrated Jitter**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 192-194, doi: 10.1109/ISSCC49657.2024.10454284.

[IEEE Link](https://ieeexplore.ieee.org/document/10454284) \

## Keypoints

- cascaded-fractional-divider technique
  - main and aux (FCW, DSM, DTC)
  - generate far-integer FCW_main + FCW_aux
    - QN is cancelled
    - INL shifted to high-frequency
    - filtered easily by the PLL BW
    - both low jitter and low frac spur
- pseudo-differential DTC
  - cancel even-order nonlinearity in each unit DTC
  - DTC_p and DTC_n are placed before the two inputs of the PD
  - DTCs are symmetrical 
  - delay range is halved
  - INL is reduced
- frac-N BB-DPLL
  - BBPD reduces the chip footprint
  - 2nd-order 15b DSM for DSM_main
    - QN is cancelled by the DTC_main and DTC_fine
  - 1st-order 15b DSM for DSM_main
    - QN is cancelled by the DTC_aux
  - DTCs
    - 6b DTC_main and DTC_fine; 3b DTC_aux
    - all pseudo-differential
    - gain cali
      - 10b DAC
      - tuning the bias voltage of a PMOS resistor
      - 3 LMS in the background
  - div-2 prescaler
    - DTC range reduction
    - multiphase generator (MPG)

## Background

- modern wireless transceivers and FMCW radar systems
  - stringent PLL integrated jitter and jitter performance
  - lower EVM
  - higher position accuracy
- frac-N PLLs
  - DTC cancels QN from DSM which controls MMD
    - the INL of DTCs causes periodic patterns --> frac spur
    - use dither to mitigate the frac spur
      - strong suppression of the frac spur
      - increase random noise --> integrated jitter
  - digital pre-distortion (DPD)
    - without increasing random noise
    - long calibration time

<img src="https://s21.ax1x.com/2024/10/10/pAJHsH0.png" width = "500" alt="Schematic of the proposed DPLL with a pseudo-differential DTC and
a cascaded fractional divider." align=center />

<img src="https://s21.ax1x.com/2024/10/10/pAJH6EV.png" width = "500" alt="Conventional single-DTC-based QN cancellation (left), proposed
pseudo-differential DTC with even-order INL cancellation (right), and measured INL
of different DTCs." align=center />

## Conclusion

**TECH**  65 nm \
**REF**  100 MHz \
**OUT**  6.5~7.5 GHz \
**REF SPUR**  -62.5 dBc \
**FRAC SPUR**  -62.1 dBc \
**POWER**  8.89 mW  \
**RMS JITTER**  143.7 fs \
**FOM**  -247.4 dB \

## Important References
> 
> *frac-N PLL with DTC with range reduction* \
> [1] W. Wu et al., “A 14nm Analog Sampling Fractional-N PLL with a Digital-to-Time Converter Range-Reduction Technique Achieving 80fs Integrated Jitter and 93fs at Near-Integer Channels,” ISSCC, pp. 444-445, Feb. 2021.
> 
> *dither* \
> [2] S. M. Dartizio et al., “A 76.7fs-lntegrated-Jitter and −71.9dBc In-Band Fractional-Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering,” ISSCC, pp. 3-4, Feb. 2023. \
> [3] Q. Zhang et al., “A Fractional-N Digital MDLL with Injection-Error Scrambling and Background Third-Order DTC Delay Equalizer Achieving −67dBc Fractional Spur,” ISSCC, pp. 226-227, Feb. 2023. \
> [4] C.-R. Ho and M. S.-W. Chen, “ A Fractional-N Digital PLL with Background-Dither-Noise-Cancellation Loop Achieving <-62.5dBc Worst-Case Near-Carrier Fractional Spurs in 65nm CMOS,” ISSCC, pp. 395-395, Feb. 2018.
> 
> *DPD* \
> [5] H. Park et al., “A 365fsrms-Jitter and -63dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/Third- Order Nonlinearity Cancelation and a Probability- Density-Shaping ΔΣM,” ISSCC, pp. 442-443, Feb. 2021. \
> [6] Z. Gao et al., “A 2.6-to-4.1GHz Fractional-N Digital PLL Based on a Time-Mode Arithmetic Unit Achieving -249.4dB FoM and -59dBc Fractional Spurs,” ISSCC, pp. 380-381, Feb. 2022.
> 
> *shift spur by 0.5* \
> [7] H.-Y. Jan et al., “A Fractional-N PLL for Multiband (0.8-6 GHz) Communications Using Binary-Weighted D/A Differentiator and Offset-Frequency Δ-Σ Modulator,” IEEE JSSC, vol. 45, no. 4, pp. 768 780, Apr. 2010.
> 
> *pseudo-diff DTC* \
> [8] A. Ba et al., “A 0.62nJ/b Multi-Standard WiFi/BLE Wideband Digital Polar TX with Dynamic FM Correction and AM Alias Suppression for IoT Applications,” IEEE RFIC, pp. 308-311, Aug. 2018.
