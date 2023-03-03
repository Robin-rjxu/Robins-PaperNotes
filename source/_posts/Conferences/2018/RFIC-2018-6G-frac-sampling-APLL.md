---
title: RFIC-2018 A 5.5-7.3 GHz Analog Fractional-N Sampling PLL in 28-nm CMOS with 75 fsrmsJitter and −249.7 dB FoM
toc: true
tags:
  - RFIC
  - 2018
  - Samsung
  - PLL
abbrlink: 48386
date: 2023-03-03 22:16:31
---

![Keypoints](https://api2.mubu.com/v3/document_image/06dfbd30-4e83-486b-a65b-a5c9a574cbb5-216525.jpg) \

##### Full Citation

W. Wu et al., "**A 5.5-7.3 GHz Analog Fractional-N Sampling PLL in 28-nm CMOS with 75 fsrmsJitter and −249.7 dB FoM**," 2018 IEEE Radio Frequency Integrated Circuits Symposium (RFIC), Philadelphia, PA, USA, 2018, pp. 6403-6408, doi: 10.1109/RFIC.2018.8428844.

[IEEE Link](https://ieeexplore.ieee.org/document/8428844/) \

## Keypoints

- DTC-based analog sampling PLL
- slope generator
  - provides well-define slope
  - determine the PLL BW
  - PFD loop for fast initial freq/phase acquisiton
- DTC compensates QN
  - gain cali with single-bit CMP
  - Vref is dynamically adjusted to track offset
  - compact and delta-V DAC
    precharge to VDD/2 and update with dithering pulse
  - reset DTC each cycle for better linearity
- reference doubler
  - background duty-cycle correction
  - pull in/back CLKFB by the DSM
- VCO with dual control voltage path
  - sampling result as the prop path
  - gm-C as the intg path

## Background

- DTC-based fractional-N PLL
  - DTC cancels QN due to DSM for the DIV
  - high gain sampling or sub-sampling phase detector (SPD)
- the DTC gain calibration is crucial
  - previous: use ADC to sample Voltage and cali DTC gain
  - PLL locking target : GM output current is zero-average
    sensitive to CMP offset

<img src="https://api2.mubu.com/v3/document_image/5fbe2e03-4122-4297-b129-a716a436e30b-216525.jpg" width = "500" alt="Proposed high performance DTC-based fractional-N analog PLL with reference doubler" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  52x2 MHz \
**OUT**  5.5 - 7.3 GHz \
**REF SPUR**  -70.1 dBc \
**FRAC SPUR**  -64 dBc \
**POWER**  18.9 mW  \
**RMS JITTER**  75 fs \
**FOM**  -249.7 dB \

## Important References

> *LMS-regression* \
> [1] D. Tasca, et al., “A 2.9-to-4.0 GHz fractional-N digital PLL with bang-bang phase detector and 560 fsrms integrated jitter at 4.5 mW power,” IEEE J. Solid-State Circuits, vol. 46, no. 12, pp. 2745–2758, Dec. 2011
> 
> *sub-sampling approach* \
> [2] K. Raczkowski et al., “A 9.2–12.7 GHz wideband fractional-N subsampling PLL in 28nm CMOS with 280fs RMS jitter,” IEEE RFIC Symp., pp. 89-92, June 2014.
> 
> *use ADC to sample voltage and calibrate the DTC gain* \
> [3] X. Gao et. Al., “A 2.7-to-4.3GHz, 0.16psrms jitter, -246.8dB FOM digital fractional-N sampling PLL in 28nm CMOS,” ISSCC Dig. Tech Papers, pp. 174-175, Feb. 2016.
