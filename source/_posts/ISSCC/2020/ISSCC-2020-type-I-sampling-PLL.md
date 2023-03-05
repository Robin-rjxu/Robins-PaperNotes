---
title: >-
  ISSCC-2020 17.5 A 12.5GHz Fractional-N Type-I Sampling PLL Achieving 58fs
  Integrated Jitter
toc: true
tags:
  - ISSCC
  - 2020
  - Polimi
  - PLL
abbrlink: 36664
date: 2023-03-05 22:34:26
---

![Keypoints](https://api2.mubu.com/v3/document_image/48e72849-c4b4-458f-84c3-897e5253a2bf-216525.jpg) \

##### Full Citation

M. Mercandelli et al., "**17.5 A 12.5GHz Fractional-N Type-I Sampling PLL Achieving 58fs Integrated Jitter**," 2020 IEEE International Solid- State Circuits Conference - (ISSCC), San Francisco, CA, USA, 2020, pp. 274-276, doi: 10.1109/ISSCC19947.2020.9063135.

[IEEE Link](https://ieeexplore.ieee.org/document/9063135) \

## Keypoints

- frac-N type-I sampling PLL
  - digital counter-based FLL
  - slope-control block for the ref
  - sampled voltage for the prop path (type-I)
  - DTC in the ref path cancels QE for frac-N freq
- type-I phase error and frac QE
  - DTC cancels frac QE with LMS gain calibration
  - the seconde DTC cancels type-I phase offset
  - leverage the phase offset that limit SPD range
  - no extra quantization noise
  - digitized phase error for the cancellation of frac QE
    DTC gain calibration
  - SPD helps to keep constant PLL BW
  - non-overlapped sampling and RC filter render low voltage ripples
- digital phase error correction (DPEC)
  - first align delayed ref_d to div by a second DTC
  - digitized the residual random noise by a 1b TDC
  - has smaller range than the SPD linear range
  - accumulate the DTC overflow  carry and tunes the VCO freq

## Background

- analog PLL : large analog filters
- digital PLL: quantization error from TDC
- analog sampling type-I  PLL
  - compact area (small filter)
  - limited range of SPD
  - tuning dependent phase error (offset)
  - type-I phase offser reduces SPD range
  - narrow PLL locking range
  - integer-N frequency

<img src="https://api2.mubu.com/v3/document_image/8c804feb-e066-403d-aeee-f4bef01c1fdf-216525.jpg" width = "500" alt="Block diagram of the presented fractional-N type-I sampling PLL" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  500 MHz \
**OUT**  11.9 - 14.1 GHz \
**REF SPUR**  -73.2 dBc \
**FRAC SPUR**  -63.2 dBc \
**POWER**  18 mW  \
**RMS JITTER**  58.2 fs \
**FOM**  -252.1 dB \

## Important References

> *digital sub-sampling PLL* \
> [3] J. Kim et al., “A 76fsrms Jitter and -40dBc Integrated-Phase-Noise 28-to-31GHz Frequency Synthesizer Based on Digital Sub-Sampling PLL Using Optimally Spaced Voltage Comparators and Background Loop-Gain Optimization,” ISSCC, pp. 258-259, Feb. 2019.
> 
> *SPD for the phase locking loop* \
> [4] A. Sharkia et al., “A 0.01mm2 4.6-to-5.6GHz Sub-Sampling Type-I Frequency Synthesizer with -254dB FOM,” ISSCC, pp. 256-257, Feb. 2018.
> 
> *DTC cancels frac QE* \
> [5] D. Tasca et al., “A 2.9-to-4.0GHz Fractional-N Digital PLL with Bang-Bang Phase Detector and 560fsrms Integrated Jitter at 4.5mW Power,” ISSCC, pp. 88- 89, Feb 2011.
