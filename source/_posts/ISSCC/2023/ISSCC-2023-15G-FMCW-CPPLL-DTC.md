---
title: >-
  ISSCC-2023 A 16GHz, 41kHzrms Frequency Error, Background-Calibrated,
  Duty-Cycled FMCW Charge-Pump PLL
toc: true
tags:
  - ISSCC
  - 2023
  - imec
  - PLL
  - FMCW
abbrlink: 30557
date: 2023-02-22 22:59:47
---

![Keypoints](https://api2.mubu.com/v3/document_image/2c9b37b6-987f-430f-8a04-381145c6a2f0-216525.jpg) \

##### Full Citation

Pratap Tumkur Renukaswamy, et al, "**A 16GHz, 41kHzrms Frequency Error, Background-Calibrated, Duty-Cycled FMCW Charge-Pump PLL**,"

## Keypoints

- archietecture
  - TPM : breaks the trade-off between BW and fast-chirp
  - 1b TDC : sign extraction
  - DTC : phase offset compensation (POC-DTC)
  - QDAC and DSM-div as chirp generation
- nonlinearity calibration
  - instantaneous charge error (Icp×Tpulse) at the CP output
  - POC-DTC  in the ‘Ref’ path
    - compensates phase offsets
    - enable 1b TDC for sign extraction
    - both Ref and Div for pos/neg
  - extracted sign for DTC gain and Kvco cali
- fast chirp
  - gear shift
  - coarse-lock-monitor output
  - LuT (DTC gain, freq code INL and Poc[k])

## Background

- battery-powered FMCW requires duty-cycled mode
  - fast startup, fast lock at the start of every chirp burst
  - minimal reset time in-between chirps
- modulation nonlinearities need calibration
  - varactor nonlinear voltage-to-capacitance conversion
  - intrinsic 1/√LC nonlinearity
  - finite current-source output impedance
  - DTC nonlinearity
-  mismatch between both CPs
  - UP/DOWN current mismatch
  - skew
  - pulse width mismatch
- reduce the QDAC resolution
  - increase the varactor linear-tuning range

<img src="https://api2.mubu.com/v3/document_image/8f56828c-7c43-4c64-b572-0ade6008ba77-216525.jpg" width = "500" alt="Block diagram of the CP-PLL FMCW synthesizer" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  80 MHz \
**OUT**  15 - 18.5 GHz \
**BW CHIRP**  1.5 GHz \
**MAX CHIRP SLOPE**  117.2 MHz/us \
**REF SPUR**  -56 dBc \
**FRAC SPUR**  -53 dBc \
**POWER**  16.5 mW \
**DUTY CYCLED POWER**  1.48/9.15 mW \
**RMS JITTER**  155.9 fs \
**FOM**  -244.7 dB \


## Important References

> *two-point modulation (TPM)* \
> [1] Z. Shen et al., “A 24GHz Self-Calibrated ADPLL-Based FMCW Synthesizer with 0.01% rms Frequency Error Under 3.2GHz Chirp Bandwidth and 320MHz/μs Slope,” ISSCC, pp. 450-451, Feb. 2021. \
> [2] P. Renukaswamy et al., “A 12mW 10GHz FMCW PLL Based on an Integrating DAC with 90kHz rms Frequency Error for 23MHz/μs Slope and 1.2GHz Chirp Bandwidth,” ISSCC, pp. 278-279, Feb. 2020.
> 
> *time-domain sign extraction with 1b TDC* \
> [3] M. Mercandelli et al., “A 12.5GHz Fractional-N Type-I Sampling PLL Achieving 58fs Integrated Jitter,” ISSCC, pp. 274-275, Feb. 2020. \
> 
> *extract DC voltage error with a DS-ADC* \
> [4] M. Gupta et al., “A 1.8-GHz Spur-Cancelled Fractional-N Frequency Synthesizer with LMS-Based DAC Gain Calibration,” IEEE JSSC, vol. 41, no. 12, pp. 2842-2851, Dec. 2006.
