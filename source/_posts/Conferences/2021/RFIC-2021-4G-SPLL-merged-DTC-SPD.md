---
title: >-
  RFIC-2021 A 3.3-4.5GHz Fractional-N Sampling PLL with A Merged Constant Slope
  DTC and Sampling PD in 40nm CMOS
toc: true
tags:
  - RFIC
  - 2021
  - ZJU
  - PLL
abbrlink: 46894
date: 2023-03-12 15:04:44
---

![Keypoints](https://api2.mubu.com/v3/document_image/e91c7d68-2dc8-408a-9e75-c70dd9f78e3a-216525.jpg) \

##### Full Citation

G. Jin, F. Feng, X. Gao, W. Chen, Y. Shu and X. Luo, "**A 3.3-4.5GHz Fractional-N Sampling PLL with A Merged Constant Slope DTC and Sampling PD in 40nm CMOS**," 2021 IEEE Radio Frequency Integrated Circuits Symposium (RFIC), Atlanta, GA, USA, 2021, pp. 63-66, doi: 10.1109/RFIC51843.2021.9490495.

[IEEE Link](https://ieeexplore.ieee.org/document/9490495) \

## Keypoints

- SPD with merged constant-slope DTC
  - take advantage of the voltage ramp in DTC
    - set the precharge voltage to cancel the QE
    - starts charging from the precharged point
    - hold point indicates the residue phase error
  - keep high gain of the SPD from voltage sampling
    - steer ramp
    - samples the divided feedback
  - LMS to set the DTC gain
    - the voltage sign are extracted
    - CMP mismatch is dynamic adjusted

## Background

- high slew rate ramp to get a high PD gain
  - sub-sampling PD
  - use DTC to realize frac with SSPD
- DTC cancels QE in time domain
  - all types of DTC experience square-ramp-square
  - SSPD needs voltage ramp
  - constant-slope DTC needs slope generator

<img src="https://api2.mubu.com/v3/document_image/d60e913e-4124-4dbd-9581-390bc5c930d8-216525.jpg" width = "500" alt="Proposed fractional-N SPLL with a merged constant slope DTC and sampling PD" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  100 MHz \
**OUT**  3.3 - 4.5 GHz \
**FRAC SPUR**  -54 dBc \
**POWER**  2.4 mW  \
**RMS JITTER**  292 fs \
**FOM**  -246.9 dB \

## Important References

> *comparator mismatch cancellation* \
> [4] W. Wu et al., “A 28-nm 75-fsrms analog fractional-N sampling PLL with a highly linear DTC incorporating background DTC gain calibration and reference clock duty cycle correction,” JSSC, May 2019.
> 
> *constant slope DTC (CS-DTC)* \
> [6] J Z. Ru et al, “A High-Linearity Digital-to-Time Converter Technique: Constant-Slope Charging,” JSSC, May. 2015.
> 
> *truncated CS-DTC* \
> [7] H. Liu et al., “A 265μW Fractional-N Digital PLL with Seamless Automatic Switching Subsampling/Sampling Feedback Path and Duty-Cycled Frequency-Locked Loop in 65nm CMOS,” ISSCC, Feb. 2019.
