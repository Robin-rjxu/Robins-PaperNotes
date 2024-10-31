---
title: >-
  VLSI-2024 A 79.3fsrms Jitter Fractional-N Digital PLL Based on a DTC Chopping
  Technique
toc: true
tags:
  - VLSI
  - 2024
  - DPLL
  - BBPD
  - DTC
  - Milano
abbrlink: 35411
date: 2024-10-31 16:36:55
---

![Keypoints](https://s21.ax1x.com/2024/10/31/pADAB4A.png) \

##### Full Citation

R. Moleri et al., "**A 79.3fsrms Jitter Fractional-N Digital PLL Based on a DTC Chopping Technique**," 2024 IEEE Symposium on VLSI Technology and Circuits (VLSI Technology and Circuits), Honolulu, HI, USA, 2024, pp. 1-2, doi: 10.1109/VLSITechnologyandCir46783.2024.10631343.

[IEEE Link](https://ieeexplore.ieee.org/document/10631343) \

## Keypoints

- DTC chopping technique
  - randomly move the DTC between the ref and div paths
  - random ±1 sequence breaks the periodicity
  - frac spurs are converted into a wide-band random noise
  - removes the in-band PLL noise from DTC flicker noise
- overflow-offset-calibration (OOC)
  - non-zero DTC fixed time offset causes a large Δt[k] variation
  - additional DTC offset-DTC
    - split between the offset-DTC and the MMD path
    - the OOC integrates e[k] to the offset-DTC
    - carry signal produces Ndco[k] and remove offset by the MMD
- frac-N BB DPLL
  - main-DTC
    - coarse and a fine VS-DTC stage
  - offset-DTC
    - coarse path-selection DTC stage
    - finer VS-DTC
  - offset-DTC range reduction technique
    - reduce the main-DTC range from Tdco/2
    - DCO falling edge with MUX and FFs
    - duty-cycle correction

## Background

- wide data-rate wireless transceivers
  - ultra-low jitter and low-spur fractional-N PLLs
  - DTC removes the quantization-error (QE)
  - VS-DTC
    - the highest noise-power FoM
    - INL can be approx. as an even function
    - ref and div path INL have swapping sign
  - large frac spur due to DTC non-linearity
- DTC non-linearity
  - digital-predistortion :  hardware resources
  - randomize the QE sequence : increased DTC delay range

<img src="https://s21.ax1x.com/2024/10/31/pADAs3t.png" width = "500" alt="Block diagram of the implemented fractional-N PLL" align=center />

<img src="https://s21.ax1x.com/2024/10/31/pADAr9I.png" width = "500" alt="proposed DTC chopping technique" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  175 MHz \
**OUT**  8.75 ~ 10.25 GHz \
**REF SPUR**  -76.4 dBc \
**FRAC SPUR**  -63.6 dBc \
**POWER**  16.7 mW  \
**RMS JITTER**  79.3 fs \
**FOM**  -249.8 dB \

## Important References

> *digital-predistortion* \
> [1] S. Levantino, JSSC 2014. 
> 
> *randomize the QE sequence* \
> [2] H. Park, ISSCC 2022.
> 
> *higher DTC noise and PLL jitter from randomization* \
> [3] W. Wu, ISSCC 2021.
> 
> *VS-DTC better noise-power FoM* \
> [4] D. Xu, CICC 2023.
> 
> *VS-DTC worse INL : slope dependent output buffer delay* \
> [5] R. Ru, JSSC 2015.
> 
> *other sub-100fs frac-PLL* \
> [6] G. Castoro, ISSCC 2023.  \
> [7] S. M. Dartizio, ISSCC 2023.  \
> [8] Y. Jo, JSSC 2023.