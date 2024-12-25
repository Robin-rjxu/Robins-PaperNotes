---
title: >-
  VLSI-2023 A 122fsrms-Jitter and −60dBc-Reference-Spur 12.24GHz MDLL with a 102
  - Multiplication Factor Using a Power-Gating Technique
toc: true
tags:
  - VLSI
  - 2023
  - MDLL
  - KAIST
abbrlink: 33698
date: 2024-12-25 22:29:58
---

![Keypoints](https://s21.ax1x.com/2024/12/25/pAvPy6g.png) \

##### Full Citation

Y. Cho, J. Lee, S. Park, S. Yoo and J. Choi, "**A 122fsrms-Jitter and −60dBc-Reference-Spur 12.24GHz MDLL with a 102 - Multiplication Factor Using a Power-Gating Technique**," 2023 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Kyoto, Japan, 2023, pp. 1-2, doi: 10.23919/VLSITechnologyandCir57934.2023.10185338.

[IEEE Link](https://ieeexplore.ieee.org/document/10185338/) \

## Keypoints

- power-gaing and AND combining the output
  - turns off the RO momentarily
  - restarts it at every reference period
  - completely resets the accumulated jitter
  - periodically places a clean edge
  - following AND simply combines outputs
- multi-functional calibrator (MFC) 
  - four calibration targets
  - in a time-interleaved manner
  - in the unit of 4TREF
  - controls all edges of SDIV4 to be aligned with the REs
  - TRO <-- largest BW avoids potential racing
- power-gating MDLL
  - phase-rotational divide-by-4 divider (PR-DIV4)
  - digitally-controlled delay line (DCDL)
    - delays SDIV4, by TDCDL generating SDCDL (2TRO)
  - single-pulse generator (SPG)
    - generates a single pulse, SSP
    - from the last pulse of SRO
    - only the last pulse
    - least jitter-sensitive
    - low power less than 100μW
    - avoid additional RO
  - BBPD
    - detect target errors
    - comparing the phases of SDIV4 and SDCDL
    - samples PDOUT with the proper edges of SOUT
  - multi-functional calibrator (MFC)
    - position and pulse width
    - hybrid accumulator (HACC)
      - AACC in the main path
      - DACC in an auxiliary path
        - compensates for leakage
        - moving VRO_A to minimal leakage

## Background

- Ring oscillator (RO)-based ILCMs and MDLLs
  - minimal silicon area
  - not foro utput frequency above 10GHz
- to generate high Fout
  - reference multiplier
    - degraded the jitter FOM
  - power-gating (PG) injection
    - very low jitter despite a large N
    - power-off periodically
    - not continuous output
    - alternative operation
    - mismatch of the two ROs --> high spur
  - MDLLs
    - high injection strength
    - max fOUT is limited by the MUX edge-switching time
  - combined implicitly with the unit cell
    - increase the output loading
    - stage delay limited
- RO control
  - AACC
    - large BW
    - high resolution
    - current leakage and mismatch
    - saw-tooth pattern
  - DACC
    - DSM + LPF
    - limited BW

<img src="https://s21.ax1x.com/2024/12/23/pAjpACF.png" width = "500" alt="Conceptual diagrams of typical MDLL and proposed PG-MDLL" align=center />

<img src="https://s21.ax1x.com/2024/12/23/pAjpF4U.png width = "500" alt="Overall architecture and timing diagram of the proposed PG-MDLL" align=center />

<img src="https://s21.ax1x.com/2024/12/23/pAjpE34.png" width = "500" alt="Block diagram of the MFC and the goal and four targets of the calibration" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  120 MHz \
**OUT** 11.04 ~ 12.24 GHz \
**REF SPUR**  -60 dBc \
**POWER**  14.7 mW  \
**RMS JITTER**  122 fs \
**FOM**  -246.6 dB \

## Important References

> *reference multiplier* \
> [1] K. M. Megawer, JSSC, Jan. 2019, pp.65-74. \
> [2] H. Kim, ISSCC, Feb. 2022, pp.382-384.
> 
> *power-gating (PG) injection* \
> [3] S. Park, ISSCC, Feb. 2022, pp.212-214.
> 
> *maximum fOUT is strictly limited by the edge-switching time of a MUX* \
> [4] S. Yang, JSSC, Jan. 2019, pp.88-98.
> 
> *the MUX was combined implicitly with the unit cell* \
> [5] R. Xu, ISSCC, Feb. 2022, pp.214-216. \
> [6] S. Yoo, JSSC, Jan. 2021, pp.490-492.