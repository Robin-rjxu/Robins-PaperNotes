---
title: ESSCIRC-2023 A 4-12.1-GHz Fractional-N Ring Sampling PLL Based on Adaptively-Biased PD-Merged DTC Achieving -37.6± 0.9-dBc Integrated Phase Noise, 261.9-fs RMS Jitter, and -240.6-dB FoM
toc: true
tags:
  - ESSCIRC
  - 2023
  - CAS
  - RO
  - PLL
  - DAC-DTC
abbrlink: 22332
date: 2023-11-15 00:04:12
---

![Keypoints](https://api2.mubu.com/v3/document_image/a4503e72-40d5-4db7-a506-2d7df4f533ce-216525.jpg) \

##### Full Citation

X. Shen et al., "**A 4-12.1-GHz Fractional-N Ring Sampling PLL Based on Adaptively-Biased PD-Merged DTC Achieving -37.6± 0.9-dBc Integrated Phase Noise, 261.9-fs RMS Jitter, and -240.6-dB FoM**," ESSCIRC 2023- IEEE 49th European Solid State Circuits Conference (ESSCIRC), Lisbon, Portugal, 2023, pp. 257-260, doi: 10.1109/ESSCIRC59616.2023.10268691.

[IEEE Link](https://ieeexplore.ieee.org/document/10268691) \

## Keypoints

- Adaptively-Biased Phase-Detector-Merged Digital-to-Time Converter (AB-PD-DTC)
  - analog-domain coefficient multiplication (A-CM)
    - VDAC --> charging current --> tuning gain
    - relax DAC resolution for QNC
    - reduce power and complexity
  - DSM --> preset  PD sampling starting point --> QNC
- PLL BW ~ proportional gain = Kpd*Kcco *Kv2i /N
  - common current bias  Ispd  ∝ Icco ∝ fout
  - Kpd = Ispd / (2pi * fref * C1)
  - Kv2i = 1/Rsc = 1/(4*fref*Cp)
  - BW ∝ 1/Rsc ∝ 1/fref (PVT-constant)
- common bias --> local feedback to track variation
- analog bias  vs. digital multiplication
- switched-cap --> frequency-dependent --> PVT-constant

## Background

- ROs have wide frequency tuning range (FTR), small area, and free of inductive coupling
- wide frequency tuning range
  - BW varies as wide-range N
  - need wide-range DTC to realize fractional operation
  - gain sampling PD varies as Fout
  - limit to use narrow-band FIR filter
- need wide bandwidth to suppress poor phase noise
  - good for phase noise
  - bad for stability

<img src="https://api2.mubu.com/v3/document_image/b1b2cd64-41ef-4343-a64c-8109796ceaea-216525.jpg" width = "700" alt="Overall Architecture of the proposed FN-RSPLL" align=center />

## Conclusion

**TECH**  40 nm \
**REF**  100 MHz \
**OUT**  4 ~ 12.1 GHz \
**REF SPUR**  -47.1 dBc \
**FRAC SPUR**  -49.61 dBc \
**POWER**  12.8 mW  \
**RMS JITTER**  261.9 fs \
**FOM**  -240.6 dB \

## Important References

> *wide-BW for reducing RO PN* \
> [6] H. Park et al., "A 365fsrms-Jitter and -63dBc-Fractional Spur 5.3GHz-Ring-DCO-Based Fractional-N DPLL Using a DTC Second/ Third-Order Nonlinearity Cancelation and a Probability-Density- Shaping ΔΣM," IEEE Int. Solid-State Circuits Conf. (ISSCC) Dig. Tech. Papers, pp. 442-444, Feb. 2021.
> 
> *FIR filter for fractional operation* \
> [7] L. Kong and B. Razavi, "A 2.4-GHz RF Fractional-N Synthesizer With BW = 0.25fREF," IEEE Journal of Solid-State Circuits, vol. 53, no. 6, pp. 1707-1718, Jun. 2018.
> 
> *DAC-DTC and SPD gain variation* \
> [8] G. Jin, et al., "A 3.3-4.5GHz Fractional-N Sampling PLL with A Merged Constant Slope DTC and Sampling PD in 40nm CMOS," IEEE Radio Frequency Integrated Circuits Symposium (RFIC), pp. 63-66, Jun. 2021.
