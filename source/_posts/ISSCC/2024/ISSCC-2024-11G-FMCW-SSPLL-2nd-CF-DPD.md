---
title: >-
  ISSCC-2024 10.7 An 11GHz 2nd-order DPD FMCW Chirp Generator with 0.051% rms Frequency Error under a 2.3GHz Chirp Bandwidth, 2.3GHz/μs Slope, and 50ns Idle Time in 65nm CMOS
toc: true
abbrlink: 27355
date: 2024-10-16 20:25:24
tags:
  - ISSCC 
  - 2024
  - FMCW
  - PLL
  - SSPD
  - SEU
---

![Keypoints](https://s21.ax1x.com/2024/10/16/pANWiqK.png) \

##### Full Citation

DX\. Wang et al., "**10.7 An 11GHz 2nd-order DPD FMCW Chirp Generator with 0.051% rms Frequency Error under a 2.3GHz Chirp Bandwidth, 2.3GHz/μs Slope, and 50ns Idle Time in 65nm CMOS**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 200-202, doi: 10.1109/ISSCC49657.2024.10454283.

[IEEE Link](https://ieeexplore.ieee.org/document/10454283) \

## Keypoints

- 2nd-order curve-fitting (2nd-CF) DPD
  - 1st-LUT ahead of the ramp integrator
    - ci is estimated with LMS
    - gi  = c_i+1 - ci
  - pre-running ramp tracker
  - multiplexer switches between the ramp tracker and the LUT
- FMCW SS-PLL of ultra-fast wideband fitting techniques
  - 2nd-CF DPD
    - dynamic track-and-hold
    - integral path in the digital loop filter (DLF)
    - voltage tracking loop (VTL) for robust LUT calibration
    - involving an integral path to the DLF in the VTL
    - three states: tracking, stablized, hold
  - zero-phase-error DTC modulator
    - accumulated phase error ACC[k] is wrapped by the DTC gain KDTC[k]
  - delay-spread calibration

## Background

- short-range 3D imaging radar systems
  - a 79GHz large-scale MIMO radar imaging system
  - quick and precise scanning
  - sub-millisecond snapshot duration
  - sub-centimeter depth resolution
- FMCW chirp generator 
  - ultra-fast chirp slope exceeding 15GHz/μs
    - 1μs chirp duration 
    - \>15GHz bandwidth (BW)
  - two-point-modulation (TPM) technique for fast chirp
    - high chirp linearity
    - narrow PLL BW for low PN
    - quick loop response
    - chirp idle time (Tidle) ~ 50ns
      - 1st-order curve-fitting (1st-CF) DPD technique
      - 1st-order look-up table (1st-LUT)
      - 0th-order LUT for ramp-rate fitting

<img src="https://s21.ax1x.com/2024/10/16/pANWPr6.png" width = "500" alt="Block diagram of the proposed FMCW synthesizer" align=center />

<img src="https://s21.ax1x.com/2024/10/16/pANWkVO.png" width = "500" alt="Block diagram of the ramp-tracker-assisted 2nd-order curve-fitting DPD" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  100 MHz \
**OUT**  9.4~12.4 GHz \
**MAX BW CHIRP**  2.3 GHz \
**MAX SLOPE**  2.3 GHz/us \
**MAX FM ERROR RMS** 1176 KHz \
**FRAC SPUR**  -52.49 dBc \
**POWER**  50.8 mW  \
**RMS JITTER**  148.7 fs \

## Important References

> *two-point-modulation (TPM) in frac PLLs* \
> [1] Z. Shen et al., “A 24GHz Self-Calibrated ADPLL-Based FMCW Synthesizer with 0.01% rms Frequency Error Under 3.2GHz Chirp Bandwidth and 320MHz/μs Slope,” ISSCC, pp.450-451, Feb. 2021. \
> [2] P. Renukaswamy et al., “A 12mW 10GHz FMCW PLL Based on an Integrating DAC with 90kHz rms Frequency Error for 23MHz/μs Slope and 1.2GHz Chirp Bandwidth,” ISSCC, pp. 278-279, Feb. 2020. (0th-order LUT for ramp-rate fitting) \
> [3] Q. Shi et al., ”A Self-Calibrated 16GHz Subsampling-PLL-Based 30μs Fast Chirp FMCW Modulator with 1.5GHz Bandwidth and 100kHz rms Error,” ISSCC, pp. 408-409, Feb. 2019. ( 1st-order look-up table (1st-LUT) for ramp fitting) \
> [4] D. Cherniak et al., “A 23-GHz Low-Phase-Noise Digital Bang-Bang PLL for Fast Triangular and Sawtooth Chirp Modulation,” IEEE JSSC, vol. 53, no. 12, pp. 3565-3575, Dec. 2018. (calibrated ramp rate and interactions among ci through the calculation of gi) \
> [5] A. Yan et al., “An 11.4-to-16.4GHz FMCW Digital PLL with Cycle-Slipping Compensation and Back-Tracking DPD Achieving 0.034% RMS Frequency Error under 3.4-GHz Chirp Bandwidth and 960-MHz/μs Chirp Slope,” IEEE Symp. VLSI Circuits, pp. 1-2, June 2023. \
> 
> *1st-order digital pre-distortion (DPD) : [2-4]* \
> 
> *ramp non-linearity of a ramp tracker : [1, 5]* \
> 
> *extract the sign of the phase noise from the output current of a Gm : [2, 3]* \
> 
> *large frequency hopping : [2, 3]* \
> 
> *voltage tracking loop * \
> 
> [6] W. Wu et al., ”A 28-nm 75-fsrms Analog Fractional-N Sampling PLL with a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction,” IEEE JSSC, vol. 54, no. 5, pp. 1254-1265, May 2019.
> 
> *delay-spread calibration* \
> [7] G. Marzin et al., “A 20 Mb/s Phase Modulator Based on a 3.6GHz Digital PLL with -36dB EVM at 5mW Power,” IEEE JSSC, vol. 47, no. 12, pp. 2974-2988, Dec. 2012.
> 
> [8] P. Renukaswamy et al., “A 16GHz, 41kHzrms Frequency Error, Background-Calibrated, Duty-Cycled FMCW Charge-Pump PLL,” ISSCC, pp. 74-75, Feb. 2023.