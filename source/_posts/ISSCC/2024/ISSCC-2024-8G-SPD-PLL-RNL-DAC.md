---
title: >-
  ISSCC-2024 10.5 A 76 fsrms- Jitter and -65dBc- Fractional-Spur Fractional-N
  Sampling PLL Using a Nonlinearity-Replication Technique
toc: true
tags:
  - ISSCC
  - 2024
  - SPLL
  - SPD
  - DAC
  - KAIST
abbrlink: 56977
date: 2024-10-13 23:14:01
---

![Keypoints](https://s21.ax1x.com/2024/10/13/pAtkRsI.png) \

##### Full Citation

Y. Shin, J. Lee, J. Kim, Y. Jo and J. Choi, "**10.5 A 76 fsrms- Jitter and -65dBc- Fractional-Spur Fractional-N Sampling PLL Using a Nonlinearity-Replication Technique**," 2024 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2024, pp. 196-198, doi: 10.1109/ISSCC49657.2024.10454557.

[IEEE Link](https://ieeexplore.ieee.org/document/10454557) \

## Keypoints

- SPD NL-replication (SNL-REP)
  - use a DAC precisely follow the non-linear output of the SPD
  - Q-error is naturally cancelled by the voltage comparator (VC)
  - currnt DAC and a capacitor C \
    the same current and C as the SPD
  - V_SPD and V_RNL-DAC have the same distorted profile
- proposed frac-N sampling PLL
  - RNL-DAC naturally cancelled by the VC
    - charge-integration DAC (QDAC)
    - remain low in-band noise
    - wide dynamic range with the full-range N and P type VCs together
      - in parallel
      - use DAC to predict the level of V_SPD and V_RNL-DAC to determine the VC
      - double tail comparator
      - calibrated input offset with LMS
  - share the same layout and close to the SPD 
- 6b fine DTC 
  - improve the compensation resolution
  - narrow range 
  - minimal peak INL
- MASH 1-1 DSM (2Tvco)
- gain calibration of the SPD and the DAC
- 1b output code of the VC is used for the DLF

## Background

- frac-N sampling PLL
  - high-gain sampling phase detector
  - reduce in-band PN
  - must remove the Q-error of the DSM
- Q-error cancellation
  - DTC in time domain
    - nonlinearity and compensation
    - digital predistortion (DPD)
    - high linear DTC: constant-slope, inverse constant-slope
  - NL and PN tradeoff
- DAC in voltage domain

<img src="https://s21.ax1x.com/2024/10/13/pAtk2QA.png" width = "500" alt="Overall architecture of the proposed fractional-N SPLL" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  150 MHz \
**OUT**  10.4~11.8 GHz \
**REF SPUR**  -69 dBc \
**FRAC SPUR**  -65 dBc \
**POWER**  15.3 mW  \
**RMS JITTER**  76 fs \
**FOM**  -250.5 dB \

## Important References

> *frac PLL with DTC* \
> [1] W. Wu et al., “A 14-nm Ultra-Low Jitter Fractional-N PLL Using a DTC Range Reduction Technique and a Reconfigurable Dual-Core VCO,” IEEE JSSC, vol. 56, no. 12, pp. 3756-3767, Dec. 2021.
> 
> *DTC NL DPD* \
> [2] S. Levantino et al., “An Adaptive Pre-Distortion Technique to Mitigate the DTC Nonlinearity in Digital PLLs,” IEEE JSSC, vol. 49, no. 8, pp. 1762-1772, Aug. 2014.
> 
> *inverse constant-slope DTC (ICS-DTC)* \
> [3] S. M. Dartizio et al., “A 76.7fs-lntegrated-Jitter and −71.9dBc In-Band Fractional-Spur Bang-Bang Digital PLL Based on an Inverse-Constant-Slope DTC and FCW Subtractive Dithering,” ISSCC, pp. 78-79, Feb. 2023.
> 
> *remove the Q-error in the voltage domain using a DAC* \
> [5] G. Castoro et al., “A 9.25GHz Digital PLL with Fractional-Spur Cancellation Based on a Multi-DTC Topology,” ISSCC, pp. 82-83, Feb. 2023. \
> [4] J. Kim et al., “A 104fsrms-Jitter and −61dBc-Fractional Spur 15GHz Fractional-N Subsampling PLL Using a Voltage-Domain Quantization-Error Cancelation Technique,” ISSCC, pp. 448-449, Feb. 2021.
> 
> *frac PLL in time mode* \
> [6] Z. Gao et al., “A 2.6-to-4.1GHz Fractional-N Digital PLL Based on a Time-Mode Arithmetic Unit Achieving -249.4dB FoM and -59dBc Fractional Spurs,” ISSCC, pp. 380-381, Feb. 2022.