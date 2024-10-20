---
title: >-
  ISSCC-2024 14.3 A 3nm Adaptive Clock Duty-Cycle Controller for Mitigating
  Aging-Induced Clock Duty-Cycle Distortion
toc: true
tags:
  - ISSCC
  - 2024
  - DCC
  - Qualcomm
abbrlink: 38776
date: 2024-10-20 20:59:38
---

![Keypoins](https://s21.ax1x.com/2024/10/20/pAaUoGT.png) \

## Full Citation

D. Yingling et al., "**14.3 A 3nm Adaptive Clock Duty-Cycle Controller for Mitigating Aging-Induced Clock Duty-Cycle Distortion**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 258-260, doi: 10.1109/ISSCC49657.2024.10454421.
[IEEE Link](https://ieeexplore.ieee.org/document/10454421) \

## Keypoints

- on-die adaptive clock duty-cycle controller (DCC) in a 3nm test chip
  - clock path
    - glitch-free MUX (GF-MUX) gates
    - a global CGC
    - an adaptive clock distribution (ACD)
  - DCC
    - duty-cycle monitor (DCM)
      - configurable launching and capturing clocks
      - tunable-delay element (TDE)
      - time-to-digital converter (TDC)
      - clock-gating circuit (CGC)
      - two measurements
        - TDE calibration
          - use tdc_q[0] only
          - binary search dcm_cfg
          - (clk_l to din)  =  (din to clk_c)
          - slow
          - wide range
        - constant TDE
          - use all tdc_q
          - constant dcm_cfg
          - dcd = difference in the tdc_q
          - fast
          - limited by TDC range
      - duty-cycle adjuster (DCA)
        - switch rise/fall by dca_cfg with XOR gates
        - high-phase extender (HPE) only
      - adaptive control

## Background

- duty cycle distortion degrades with aging
  - the rising and falling clock-path delays change differently due to transistor aging
  - clock-path length and the stress time, voltage (VDD), and temperature
  - need an on-die system to monitor clock-leaf nodes and adjust the clock duty cycle
- ring-oscillator-based duty-cycle detector
  - precise resolution
  - long measurement time
  - interface with a clock shaper circuit

<img src="https://s21.ax1x.com/2024/10/20/pAaUIiV.png" width = "500" alt="block diagram of the adaptive clock duty-cycle controller (DCC)" align=center />

<img src="https://s21.ax1x.com/2024/10/20/pAaU4I0.png" width = "500" alt="Duty-cycle monitor (DCM) and duty-cycle adjuster (DCA) circuits" align=center />

## Conclusion

**TECH**  3 nm \
**SUPPLY**  0.65 V \
**IN/OUT**  1 GHz \
**POWER**  0.127 mW \
**RESOLUTION**  2 inverter \
**RANGE**  64 x \

## Important References

> *the rising and falling clock-path delays change differently due to transistor aging* \
> [1] J. Tschanz et al., “Tunable Replica Circuits and Adaptive Voltage-Frequency Techniques for Dynamic Voltage, Temperature, and Aging Variation Tolerance,” IEEE Symp. VLSI Circuits, pp. 112-113, 2009.
> 
> *ring-oscillator-based duty-cycle detector* \
> [2] H. Chen et al., “A 7nm 5G Mobile SoC Featuring a 3.0GHz Tri-Gear Application Processor Subsystem,” ISSCC, pp. 54-55, 2021.
> 
> *adaptive clock duty-cycle controller (DCC)* \
> [3] S.-Y. Wu et al., “A 3nm CMOS FinFlexTM Platform Technology with Enhanced Power Efficiency and Performance for Mobile SoC and High Performance Computing Applications,” IEEE IEDM, pp. 639-642, 2022.
> 
> *binary search to tune the timing margin* \
> [4] K. A. Bowman et al., “A 16 nm All-Digital Auto-Calibrating Adaptive Clock Distribution for Supply Voltage Droop Tolerance Across a Wide Operating Range,” IEEE JSSC, vol.51, no. 1, pp. 8-17, 2016.