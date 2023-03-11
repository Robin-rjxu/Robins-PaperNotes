---
title: >-
  CICC-2020 A 7.7~10.3GHz 5.2mW -247.3dB-FOM Fractional-N Reference Sampling PLL
  with 2nd Order CDAC Based Fractional Spur Cancellation In 45nm CMOS
toc: true
tags:
  - CICC
  - 2020
  - AuburnU
  - PLL
abbrlink: 42674
date: 2023-03-10 20:09:47
---

![Keypoints](https://api2.mubu.com/v3/document_image/b6567825-913a-4e3f-b1d3-9cdf5252598b-216525.jpg) \

##### Full Citation

D. Liao and F. F. Dai, "**A 7.7~10.3GHz 5.2mW -247.3dB-FOM Fractional-N Reference Sampling PLL with 2nd Order CDAC Based Fractional Spur Cancellation In 45nm CMOS**," 2020 IEEE Custom Integrated Circuits Conference (CICC), Boston, MA, USA, 2020, pp. 1-4, doi: 10.1109/CICC48029.2020.9075927.

[IEEE Link](https://ieeexplore.ieee.org/document/9075927) \

## Keypoints

- reference sampling phase detector
  type-I PLL
  - reshape buffer
    - tune slope for large detection range
      one VCO cycle 
    - trade-off between range and gain
    - large for fast acquisition and small for high gain
    - CML logic
  - CDAC and the sampling capacitor are naturally merged
    - reset to Vref/ground
    - samples Sref as voltage
    - compensate QE with CDAC
    - hold and connect the VCO
- 2nd-order CDAC-based QE cancellation
  - CDAC gain should match QE
  - remove slope gen nonlinearity
    RC charge/discharge ramp
  - toggle CDAC bottom plate separately in sample and hold phase
  - realize an equivalent 2nd-order curve
    Vcanceller = Vref1·Qe + (Vref2 - Vref1)·Qe^2
  - equivalent to predistortion
  - possible to use LMS and fine DAC for Vref1 and Vref2

## Background

- conventional analog PLL
  - poor PD gain
- SS PLL
  - high PD gain
  - limited linear range
  - poor frequency acquisition
- sampling reference 
  - low PD gain
  - wider linear range
- fractional operation
  - compensate in time domain
    - with DTC
      - noise is not suppressed by PD gain
      - nonlinearity
    - with PI
      - current PI : poor linearity, high power
      - integration PI : complex and poor noise

<img src="https://api2.mubu.com/v3/document_image/1362ae3c-afe1-426b-a1cb-9f47ca2a77cb-216525.jpg" width = "500" alt="Block diagram of the proposed frac-N type-I reference sampling PLL architecture with CDAC quantization error cancellers" align=center />

## Conclusion

**TECH**  45 nm \
**REF**  80 MHz \
**OUT**  7.7 - 10.3 GHz \
**FRAC SPUR**  -56 dBc \
**POWER**  5.2 mW  \
**RMS JITTER**  190 fs \
**FOM**  -247.3 dB \

## Important References

> *PI-based frac PLL* \
> [4] A. Narayanan, et al., "A Fractional-N Sub-Sampling PLL using a Pipelined Phase-Interpolator With an FoM of -250 dB," IEEE J. Solid-State Circuits, vol. 51, no. 7, pp. 1630-1640, Jul. 2016
> 
> *sampling phase detector (RSPD)* \
> [5] J. Sharma, et al., "A divider-less reference-sampling RF PLL with −253.5dB jitter FOM and <-67dBc Reference Spurs," ISSCC Dig. Tech Papers, pp. 258-260, Feb. 2018.
