---
title: >-
  ISSCC-2021 32.4 A 104fsrms-Jitter and -61dBc-Fractional Spur 15GHz
  Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error
  Cancelation Technique
toc: true
tags:
  - ISSCC
  - 2021
  - KAIST
  - PLL
abbrlink: 25568
date: 2023-03-08 00:44:21
---

![Keypoints](https://api2.mubu.com/v3/document_image/6f12a95b-1a36-4cbd-8199-50e59b9d4343-216525.jpg) \

##### Full Citation

J. Kim et al., "**32.4 A 104fsrms-Jitter and -61dBc-Fractional Spur 15GHz Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error Cancelation Technique**," 2021 IEEE International Solid- State Circuits Conference (ISSCC), San Francisco, CA, USA, 2021, pp. 448-450, doi: 10.1109/ISSCC42613.2021.9365815.

[IEEE Link](https://ieeexplore.ieee.org/document/9365815) \

## Keypoints

- voltage-domain Q-error cancellation (VD-QEC)
  - DAC noise can be suppressed by high PD gain
  - need to maintain PD work in high-gain region
- dual-clock-phase-sampling (DCP sampling)
  ensure always high PD gain
  - Sref and a Tdco/4 delayed clock
  - the DCDL has much less contribution to the in-band noise than a DTC
- second-order curve-fitting digital pre-distortion (SCF-DPD) 
  always fitting the DCO waveform accurately
  - make VREF to follow the nonlinear waveform of SDCO,BUF
  - the SCF-DPD to pre-adjust its output code, DDPD
  - 2nd-order polynomial a, b, and c (DDPD = a·DQF^2+b·DQF+c)
  - 13-times higher accuracy than a 1st-order fitting

## Background

- subsampling PLL has better in-band PN due to high PD gain
  - frac operation easily shifts the sampling point out of the narrow linear range
  - need dedicated quantization error correction
- time-domain quantization error cancellation
  - use DTC to compensate the quantization error
  - DTC PN is out-of-loop and not suppressed by the high PD gain
- reference sampling has smaller PD gain
- voltage domain QEC
  - adjust Vref of the CMP
  - DAC is after the PD and its noise is suppressed by the high PD gain
  - but PD gain also varies with the sampling point


<img src="https://api2.mubu.com/v3/document_image/a40a46e0-828f-4aee-9b37-42c988bd609a-216525.jpg" width = "500" alt="Overall architecture of the proposed fractional-N SSPLL (top) and the mechanism of the DCP generator (bottom)" align=center />

<img src="https://api2.mubu.com/v3/document_image/f4197d90-2fda-453a-966b-d4424c1add0d-216525.jpg" width = "500" alt="second-order curve-fitting digital pre-distortion (SCF-DPD)" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  150 MHz \
**OUT**  14 - 16 GHz \
**FRAC SPUR**  -61 dBc \
**POWER**  7.3 mW  \
**RMS JITTER**  104 fs \
**FOM**  -251 dB \

## Important References

> *time-domain Q-error cancellation (TD-QEC)* \
> [1] S. Levantino et al., “An Adaptive Pre-Distortion Technique to Mitigate the DTC Nonlinearity in Digital PLLs,” IEEE JSSC, vol. 49, no. 8, pp. 1762-1772, Aug. 2014.
> 
> *reference-sampling PLLs (RSPLLs) with smaller PD gain* \
> [2] W. Wu et al., “A 28-nm 75-fsrms Analog Fractional-N Sampling PLL With a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction,” IEEE JSSC, vol. 54, no. 5, pp. 1254-1265, May 2019. \
> [3] D. Liao et al., “A 7.7~10.3GHz 5.2mW −247.3dB-FOM Fractional-N Reference Sampling PLL with 2nd Order CDAC Based Fractional Spur Cancellation In 45nm CMOS,” IEEE CICC, pp. 1-4, Mar. 2020.
> 
> *voltage domain provides better suppression of QNC related PN* \
> [4] A. Santiccioli et al., “ Power-Jitter Trade-off Analysis in Digital-to-Time Converters,” IET Electronics Letters, vol. 53, no. 4, pp. 306-308, Mar. 2017.
