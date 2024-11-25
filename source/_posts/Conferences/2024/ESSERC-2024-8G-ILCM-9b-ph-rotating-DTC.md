---
title: >-
  ESSERC-2024 An 8 GHz 9 bit Phase-Rotating ILCM with DTC Range Reduction for
  High-Speed Serial Links
toc: true
tags:
  - ESSERC
  - 2024
  - ILCM
  - MPCG
  - DTC
  - SNU
abbrlink: 62678
date: 2024-11-25 15:12:29
---

![Keypoints](https://s21.ax1x.com/2024/11/25/pAhYZQg.png)

##### Full Citation

J. Park, J. Kim, S. Lee, K. Kim, H. -J. Park and W. -S. Choi, "**An 8 GHz 9 bit Phase-Rotating ILCM with DTC Range Reduction for High-Speed Serial Links**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 625-628, doi: 10.1109/ESSERC62670.2024.10719537.

[IEEE Link](https://ieeexplore.ieee.org/document/10719537) \

## Keypoints

- RO-based phase-rotating ILCM (PR- ILCM)
  - blocks
    - DTC
      - phase rotation
      - multi-phase clocks
        - shift using a single DTC
        - instead of multiple PIs
      - control word from
        - CDR
        - code search logic
      - two inverters with SW MOS capacitors
    - RO-based ILCM
      - frequency multiplication
      - multi-phase generation
      - PD
        - DCDL gain calibration in FDIV
        - for ILCM frequency and delay calibration
      - injected RO
        - adjustable injection strength
        - 2-stage inv-based variable delay cells
        - programmable injection gating frequency
        - spurs due to the periodic gating operation
    - calibration logic
      - pulse-gating technique
      - accurate frequency calibration
      - PD input path delay mismatch cancellation
  - features
    - frequency multiplication
    - multi-phase generation
    - infinite phase shift
      - phase accumulator for rollover
      - DTC is supposed to give exactly 2π delay 
      - need background calibration for the DTC gain
    - benefits
      - eliminates the need for 
        - multiple PIs
        - duty cycle corrector
        - additional multi phase generator (MPG)
      - allows low-frequency global clock distribution
      - power savings for multi-lane RXs
  - infinite phase rotation with DTC
    - phase rollover
      - add/subtract by Tdco/2
      - shift the injection pulse from the rising/falling edge
    - rollover code search logic process
      - starts only when the DTC code approaches near the min/max bound
      - coarse/fine  search region (steps)
      - update according to the PD output
    - optimal rollover code
      - periodically delayed by an estimated rollover code
      - error extraction
        - compare with the target injection edge after rollover
        - injection pulse gating
        - different rollover codes for rising/falling edge
        - no need for DCC
- Multi-lane RX Architecture with PR-ILCM
  - global PLL --> FDIV -->  DTC --> ILCM
  - low-frequency single-phase -> 8x frequency 4-phase
    - DTC controls the clock phase
    - accumulating the phase error from the CDR logic
    - the delayed clock is injected into the ILCM
    - DTC range
      - limits CDR phase tracking ability
      - code search logic --> infinite phase shift ability
  - fractional divider (FDIV)
    - output 1 GHz in the prototype
    - control by the CDR's integral path
    - compensate for the  frequency offset between TX and RX
    - multi-modulus divider
    - 8-bit gain-calibrated DCDL

## Background

- high-bandwidth wireline communication
  - high-speed sub-rate architecture for the transmitter (TX) and receiver (RX)
  - low-jitter multi-phase clocks
  - increasing data rate --> reduced symbol duration
  - accurate phase control in the CDR
- multi-lane RX clock distribution architecture
  - high-frequency multi-phase clocks
    - distributed from a global clock generator
    - local phase interpolators (PIs)
  - multi-phase generators
    - RO-based injection-locked oscillators ILOs
    - generate low-noise multi-phase clocks for PI inputs locally
  - high-frequency global clock distribution
    - high power
    - PI limits local CDR performance
      - PI linearity and resolution
      - slew rate
      - quadrature input phase error
      - output time constant
      - requires large area and power
  - multiple PIs
    - in each lane
    - for phase error detection and data recovery

<img src="https://s21.ax1x.com/2024/11/25/pAhYFFP.png" width = "500" alt="Proposed multi-lane RX architecture with RO-based PR-ILCM" align=center />

<img src="https://s21.ax1x.com/2024/11/25/pAhYkJf.png" width = "700" alt="Proposed RO-based PR-ILCM architecture and DTC code rollover" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  1 GHz \
**OUT**  8.0 GHz \
**REF SPUR**  -72 dBc \
**FRAC SPUR**  -55 dBc \
**POWER**  10.1+1.26 mW \
**RMS JITTER**  400 fs \
**FOM**  -241 dB \

## Important References

> *global clock generator to local phase interpolators (PIs)* \
> [1] P. Upadhyaya et al., “3.3 A 0.5-to-32.75Gb/s flexible-reach wireline transceiver in 20nm CMOS,” in 2015 IEEE International Solid-State Circuits Conference - (ISSCC) Digest of Technical Papers, 2015, pp. 1–3.
> 
> *a high-frequency single-phase clock to each lane* \
> [2] Z. Wang, Y. Zhang, Y. Onizuka, and P. R. Kinget, “A high-accuracy multi-phase injection-locked 8-phase 7GHz clock generator in 65nm with 7b phase interpolators for high-speed data links,” in 2021 IEEE International Solid-State Circuits Conference (ISSCC), vol. 64, 2021, pp. 186–188.
> 
> *RX with fractional divider* \
> [3] J. Kim et al., “A 4x32Gb/s 1.8pJ/bit collaborative baud-rate CDR with background eye-climbing algorithm and low-power global clock distribution,” arXiv preprint arXiv:2404.07021, 2024.
> 
> *pulse-gating technique for accurate RO frequency calibration* \
> [4] A. Elkholy, M. Talegaonkar, T. Anand, and P. Kumar Hanumolu, “Design and analysis of low-power high-frequency robust sub-harmonic injection-locked clock multipliers,” IEEE Journal of Solid-State Circuits, vol. 50, pp. 3160–3174, 2015. (RO frequency calibration)
> 
> *LMS-based DTC calibration* \
> [5] R. Gautam, J. D. Bandarupalli, and S. Saxena, “A 2.5–5GHz injection-locked clock multiplier with embedded phase interpolator in 65nm CMOS,” in 2020 IEEE International Symposium on Circuits and Systems (ISCAS), 2020, pp. 1–5.
> 
> *two variable frequency dividers and DCDLs and control logic for seamless phase switching* \
> [6] K. Fukuda et al., “A 12.3-mW 12.5-Gb/s complete transceiver in 65-nm CMOS process,” IEEE Journal of Solid-State Circuits, vol. 45, pp. 2838–2849, 2010.
> 
> *DTC implementation* \
> [7] A. Elmallah, M. G. Ahmed, A. Elkholy, W.-S. Choi, and P. K. Hanumolu, “A 1.6ps peak-INL 5.3ns range two-step digital-to-time converter in 65nm CMOS,” in 2018 IEEE Custom Integrated Circuits Conference (CICC), 2018, pp. 1–4.
>
> *ILCMs* \
> [8] G. Anzalone, E. Monaco, G. Albasini, S. Erba, and A. Mazzanti, “A 0.2–11.7GHz, high accuracy injection-locking multi-phase generation with mixed analog/digital calibration loops in 28nm FDSOI CMOS,” in ESSCIRC Conference 2016: 42nd European Solid-State Circuits Conference, 2016, pp. 335–338. \
> [9] Y.-C. Huang and B.-J. Chen, “30.7 An 8b injection-locked phase rotator with dynamic multiphase injection for 28/56/112Gb/s Serdes application,” in 2019 IEEE International Solid-State Circuits Conference - (ISSCC), 2019, pp. 486–488.