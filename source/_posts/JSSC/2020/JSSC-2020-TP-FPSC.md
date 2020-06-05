---
title: >-
  JSSC-2020 A Low-Jitter and Low-Reference-Spur Ring-VCO Based Injection-Locked
  Clock Multiplier Using a Triple-Point Background Calibrator
toc: true
tags:
  - JSSC
  - 2020
  - ILCM
  - KAIST
  - UNIST
abbrlink: 21341
date: 2020-06-05 00:26:18
---

![Keypoints](https://img.mubu.com/document_image/29866003-7f86-4d1a-b2aa-5b6f2a64bd90-216525.jpg) \

##### Full Citation

S. Yoo, S. Choi, Y. Lee, T. Seong, Y. Lim and J. Choi, "A Low-Jitter and Low-Reference-Spur Ring-VCO- Based Injection-Locked Clock Multiplier Using a Triple-Point Background Calibrator," in IEEE Journal of Solid-State Circuits, doi: 10.1109/JSSC.2020.2995326.[IEEE Link](https://ieeexplore.ieee.org/document/9103008) \

## Keypoints

- the triple-point frequency/phase/slope calibrator (TP-FPSC)
  - accurately remove the three root causes of the frequency errors
    - frequency drift
    - phase offset
    - slope modulation
      - the slope of the injection signal changes the propagation delay of an inverter chain
  - suppression to the in-band phase noise
  - wide bandwidth of the injection-locking for very low-RMS jitter

## Background

- a ring VCO-based ILCM
  - benefits
    - low jitter
      - free-running VCO is corrected naturally by reference signals
  - drawbacks
    - the phase-realignment has no capability of frequency correction
    - the RMS jitter and reference spur can be significantly degraded by drifted frequency
    - very difficult to reduce the level of the spur sufficiently for a high N
  - requirements
    - higher data rates
    - even more stringent peak-to-peak jitte
    - minimize reference spur level
    - precise and versatile background calibrator removes all three root causes of f_ERR
      - frequency drift due to voltage and temperature fluctuations
      - phase offset due to any systematic errors of calibrators
      - slope modulation due to the periodic injection of a reference signal
  - solutions
    - dedicated calibrator that can correct f_VCO continuously in the background

## Proposed

- ring-VCO-based ILCM
  - can achieve a low-reference spur and low-RMS jitter
  - with a background triple-point frequency/phase/slope calibrator (TP-FPSC)

## Details

- **Principle**
  - three roots causes of frequency error
    - **frequency drift**
      - conventional frequency calibrators failed to completely remove f_DF
        - limited accuracy of the calibration
          - mismatches of the delay cells
          - input offsets of a PD
          - mismatches of differential signal paths
    - **phase offset**
      - causes
        - systematic errors
          - the calibrator reacts as if this phase error was generated due to f_DF
          - tune f_VCO to reduce the phase error
          - results in the generation of f_ERR
      - existing improvements
        - pulse-gating technique
        - use additional calibrating circuits
    - **slope modulation**
      - the change in SL_INJ changes the propagation delay of an inverter chain [31]
      - ultimately causing the phase error in φPD [1]
      - conventional frequency calibrator reacts to generate more f_ERR
- **Architecture**
  - a five-stage ring VCO
  - the proposed TP-FPSC
    - voltagecontrolled delay line (VCDL)
    - bang-bang PD (BBPD)
    - a multi-control voltage (VC) generator (MVG)
      - generates three independent VCs delivered to a different target circuit for the three calibration mechanisms
        - VC1 is used for the VCO to make fVCO close to N · fREF
        - VC2 is used for the VCDL to cancel the phase offset from any systematic errors
        - VC3 is used for the slope controller to equalize the slopes of SOUT
      - three D-flip-flops (DFFs) to sample PDOUT from the PD sequentially
        - extracted error information from the same output
      - analog accumulator (A-ACC)
        - all three VCj s are updated concurrently during a short pulse PSUD
        - enhance the resolution just by decreasing the pulsewidth of PSUD
- **Operation**
  - Three Error Detection Mechanisms of the TP-FPSC
    - frequency drift
      - when the first rising edges of SOUT and SVCDL or the second rising edges of SOUT and SVCDL are compared by the PD
    - phase offset
      - φPD becomes constant for all rising edges of SOUT and SVCDL after fERR calibration is done
      - use FE4 to sample PDOUT, which generates DER2
    - slope modulation
      - after the two foregoing calibrations are done
      - detected by sampling PDOUT by FE2
    - bandwidth design
      - the three calibrating loops were designed to have different bandwidth (settling speeds) of VC1,2,3
      - largest BW of frequenc calibrator to suppress the flicker noise of the VCO
      - BW of the phase-offset calibration was ten times smaller than that of the frequency calibration
      - BW of the slope calibration was the smallest
- **Implementation**
  - slope controller
    - three current-starved inverters
    - NAND gate
    - simple inverters
    - control the slope of SINJ
      - by adjusting the bias voltage, VC3
      - the transistors of the three current-starved inverters
  - ring oscillator
    - five stage delay cell
      - digitally controlled capacitor bank, CBANK1
      - continuously adjusted by VC1 varactor, CVAR1
    - embedded multiplexer in the delay cell
      - enables that the first delay cell periodically receives the injection signal, SINJ
- **Noise Modeling**
  - phase realignment by the injection locking
  - three parallel calibration loops
    - frequency drift
    - phase offset
    - slope modulation
  - principles
    - two different time domains: f_REF, f_VCO
    - bridge time domains: ZOH reconstructors
    - the BBPD has different gains according to the variation in the jitter at the input each moment
- **Limitation**
  - the bandwidths of the three calibrators are limited by the loop stability and the detection sequence
    - frequency drift cancelled first, then phase offsets are reduced
    - only f_ERR and phi_ERR are free, the residual error is considered from the slope modulation
    - error detection race
  - the maximum fVCO could be limited due to the use of window signals

![Overall Architecture](https://img.mubu.com/document_image/b292b516-7cf3-449f-b9af-b7d0bd910185-216525.jpg) \

![Noise Model](https://img.mubu.com/document_image/4e526d53-abc5-4a91-b00c-e9e231ff3af9-216525.jpg) \

![Implementation of the TP-FPSC](https://img.mubu.com/document_image/23bc21f9-ba2d-4357-8858-39936e37b355-216525.jpg) \

![Ring-based VCO](https://img.mubu.com/document_image/96f2e53e-3ab7-437d-8d9c-19130c73f0c9-216525.jpg) \

## Conclusion

**TECH** 65nm \
**REF** 100MHz \
**OUT** 2.2-2.5 GHz \
**REF SPUR** -72 dBc \
**POWER** 11 mW \
**RMS JITTER** 142 fs \
**FOM** -246.7 dB \

## Important References
>
> *ISSCC conference paper*
>
> - [3] D. Yang et al., “16.6 a calibration-free triple-loop bang-bang PLL achieving 131fsrms jitter and-70dBc fractional spurs,” in IEEE Int. Solid-State Circuits Conf. (ISSCC) Dig. Tech. Papers, Feb. 2019, pp. 266–267. \
>
> noise mechanism of ILCM
>
> - [13] S. Ye, L. Jansson, and I. Galton, “A multiple-crystal interface PLL with VCO realignment to reduce phase noise,” IEEE J. Solid-State Circuits, vol. 37, no. 12, pp. 1795–1803, Dec. 2002. \
>
> *impact of the phase offset to the reference spur*
>
> - [15] B. M. Helal, C.-M. Hsu, K. Johnson, and M. H. Perrott, “A low jitter programmable clock multiplier based on a pulse injection-locked oscillator with a highly-digital tuning loop,” IEEE J. Solid-State Circuits, vol. 44, no. 5, pp. 1391–1400, May 2009. \
>
> *slope modulation mechanism*
>
> - [31] M. Rezzoug, J. M. Daga, and D. Auvergne, “Signal transition time effect on CMOS delay evaluation,” IEEE Trans. Circuits Syst. I, Fundam. Theory Appl., vol. 47, no. 9, pp. 1362–1369, Sep. 2000. \
>
> discrete time domain noise analysis
>
> - [32] A. Santiccioli, C. Samori, A. L. Lacaita, and S. Levantino, “Time-variant modeling and analysis of multiplying delay-locked loops,” IEEE Trans. Circuits Syst.I,Reg.Papers, vol. 66, no. 10, pp. 3775–3785, Oct. 2019. \
