---
title: >-
  ISSCC-2015 15.5 A 0.6V 1.17ps PVT-tolerant and synthesizable time-to-digital
  converter using stochastic phase interpolation with 16× spatial redundancy in
  14nm FinFET technology
toc: true
tags:
  - ISSCC
  - 2020
  - Samsung
  - TDC
abbrlink: 7786
date: 2020-08-19 22:04:21
---



#### Citation

- S. Kim, W. Kim, M. Song, J. Kim, T. Kim and H. Park, "15.5 A 0.6V 1.17ps PVT-tolerant and synthesizable time-to-digital converter using stochastic phase interpolation with 16× spatial redundancy in 14nm FinFET technology," 2015 IEEE International Solid-State Circuits Conference - (ISSCC) Digest of Technical Papers, San Francisco, CA, 2015, pp. 1-3, doi: 10.1109/ISSCC.2015.7063035. [IEEE Link](https://ieeexplore.ieee.org/document/7063035) \ 

## Keypoints

![Keypoints](https://api2.mubu.com/v3/document_image/deb72856-42f7-4c81-90bf-d35fbcc0242a-216525.jpg) \

## Notes
- high-resolution TDC  
  minimize the unit delay of quantization
  
  - Vernier delay-line-based TDC
    - limited by mismatch
    - require additional calibration
  - time-domain SAR scheme
    - too much power/area
  - time-amplifier-based multi-step TDC
    - power-hungry
    - inaccurate and PVT vulnerable
    - additional calibration
  
- proposed TDC
  - features
    - using stochastic phase interpolation
    - quantization by counting rising edges
    - 16x spatial redundancy
    - low power and PVT-variation-tolerant
  - phase interpolator
    - 2^N delay cells (effective N-m, mx redundancy)
    - timing
      - reference clock CLK_IN (T_0)

      - effective resolution T_0/2^(N-m)
    - principle
      - After the first rising edge of CLK_IN arrives at the output of the last delay cell
      - 2^N times interpolated phases can be collected from each output of the delay cells
    - non-ideality
      - poor linearity performance
        - hard to expect that the 2^N interpolated phases are uniformly distributed within one clock period
      - solution : stochastic phase interpolation
        - m LSB bits are truncated from the output
        - the final output code, DOUT, of the TDC is (N-m) bits
        - 2^m times redundancy
    - mismatch theory
      - mismatch follows Gaussian distribution
        - the delay of delay cell Td\[i\]
          ![equation-1](https://api2.mubu.com/v3/document_image/8fbb4f39-4653-47ca-9653-3f59501d700b-216525.jpg)

        - Td\[i\] also experiences a dynamic random variation  
          including device noise / jitter
          ![equation-2](https://api2.mubu.com/v3/document_image/7c41522f-c1e4-4414-a112-ae42a3c445b1-216525.jpg)
      - errors accumulated as propagating through stages  
  overall PDF can be uniformized due to the accumulation

      ![equation-3](https://api2.mubu.com/v3/document_image/0b46e4d8-853b-48a8-aa3b-636f31334746-216525.jpg)
  - measurement setup
    - sampling frequency F_s = 100 MHz
    - reference CLK_IN = 850 MHz
    - input time difference ramp
    - two external clock generators
      - frequencies are slightly different (100MHz and 99.995MHz)
  
- Figures
  
  - ![System Block](https://api2.mubu.com/v3/document_image/3d4bc1fa-03b5-4abd-8848-45a09e5cde3c-216525.jpg)




## Conclusion

**Technology** 14nm FinFET

**Bits** 10

**Resolution** 1.17 ps

**Speed** 100 MS/s

**Power** 0.78 mW

**DNL/INL** 0.8/2.3 LSB

**N_linear** 8.28

**FoM** 0.025



## References

> *vernier TDC*
>
> - \[1\] L. Vercesi, A. Liscidini, et al., “Two-Dimensions Vernier Time-to-Digital Converter,” IEEE J. Solid-State Circuits,” vol. 45, no. 8, pp. 1504-1512, Aug. 2010.
>
> *time domain SAR scheme*
> 
> - \[2\] H. Chung, H. Ishikuro, et al., “A 10-bit 80-MS/s Decision Select Successive Approximation TDC in 65-nm CMOS,” IEEE J. Solid-State Circuits, vol. 47, no. 5, pp. 1232–1241, May 2012.
> 
> *time-amplifier-based multi-step TDC*
> 
> - \[3\] K.-S. Kim, W.-S. Yu, et al., “A 9 bit, 1.12 ps Resolution 2.5 b/Stage Pipelined Time-to-Digital Converter in 65 nm CMOS Using Time-Register,” IEEE J. SolidState Circuits, vol. 49, no. 4, pp. 1007-1016, Apr. 2014.
> - \[4\] S.-J. Kim, T. Kim, et al., “A 0.63ps, 12b, Synchronous Cyclic TDC using a Time Adder for On-chip Jitter Measurement of a SoC in 28nm CMOS Technology,” IEEE Int. Symp. VLSI Circuits Dig., 2014.