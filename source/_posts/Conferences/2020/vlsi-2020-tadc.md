---
title: >-
  VLSI-2020 Open-Source Synthesizable Analog Blocks for High-Speed Link Designs
  20-GS/s 5b ENOB Analog-to-Digital Converter and 5-GHz Phase Interpolator
toc: true
tags:
  - VLSI
  - 2020
  - ADC
  - Stanford
abbrlink: 13819
date: 2020-08-20 01:05:30
---

#### Citation

S. Kim, Z. Myers, S. Herbst, B. Lim and M. Horowitz, "Open-Source Synthesizable Analog Blocks for High-Speed Link Designs: 20-GS/s 5b ENOB Analog-to-Digital Converter and 5-GHz Phase Interpolator," 2020 IEEE Symposium on VLSI Circuits, Honolulu, HI, USA, 2020, pp. 1-2, doi: 10.1109/VLSICircuits18222.2020.9162800.  [IEEE Link](https://ieeexplore.ieee.org/document/9162800) \

## Keypoints

![Keypoints](https://api2.mubu.com/v3/document_image/da7f0b69-77fa-4ef2-9ea9-c050c2baaa97-216525.jpg) \

## Notes

- ASICs of high-speed transceivers
  - expensive, hard to verify and inflexible
- proposed open-source portable generator for a high-speed link transceiver
  - digital standard cells
  - digital PnR tools
  - no precision analog design
- blocks
  - V2T for input voltage to time difference
  - PF (phase folder) : folds two input T_INP and T_INN to an unsigned pulse P_IN
  - V2T for clock generation
  - STDC (stochastic TDC)
- **STDC**
  - principle
    - quantizes the width of PIN by counting the number of delayed clock edges it contains
    - contains 255 non-precise unit inverters
    - quasi-uniform distribution of clock edges
      - inherent immunity against device mismatch, jitter, and PVT variation
      - good fit for an automated PnR flow
  - absolute value and offset
    - subtracted is calculated through a background adaptation loop
    - based on a histogram of output codes from the ADC
- **PI**  
  generate and adjust sampling clocks for the multi-channel ADC
  - 32 delayed phases from the delay chain
  - two phase blenders for the 16 odd and 16 even phases, respectively
  - arbiters finds the number of delays to control the phase mixer
  - phase mixer
    - boundary mixer: generate an average edge between its inputs
    - other mixers: act as buffers to achieve monotonic phase rotation
  - encoder
    - controls the phase mixers, the mux network, and the phase blender
    - based on the input control code and the quantized period from the arbiters
  - non-ideality
    - non-monotonic
      - from mismatch among accumulated path delays
      - even exceeds the unit delay of the delay chain (TD)
    - solution: off-chip calibration
      - detected and corrected after fabrication
      - by adding an arbiter to the input of the phase blender
      - adjusting the strength of the delay buffer for the corresponding path
- **overall ADC**
  - 16 ADCs in 4 groups
  - each group havs 4 ADC slices
  - two-stage passive T&H
  - 4 PIs
    - take a quarter-rate input clock
    - generate 5 GHz quadrature sampling clock phases
  - aligner synchronize output data
  - Look up table based static non-linearity calibration by on-chip SRAM
  - bias for input V2Ts
- implementation
  - described entirely in SystemVerilog
  - verified through Verilog simulation
  - event-driven functional models for analog blocks
  - automatic PnR

## Figures

![TDC](https://api2.mubu.com/v3/document_image/cc61e362-ca3a-4b45-91ac-88805408a6fc-216525.jpg)

![ADC](https://api2.mubu.com/v3/document_image/b1ecaba2-9704-4920-8f52-8840da3a52b4-216525.jpg)

## Conclusion

**Process**    16 FinFET \

**Speed**    20 GHz \

**ENOB**    5.6 \

**Power**    175 mW \

**FoM**    0.18 pJ/b \

**Area**    0.1 \

**Synthesizable**    Yes \

## References

> *open source project*
>
> - \[1\] DragonPHY project, https://github.com/StanfordVLSI/dragonphy