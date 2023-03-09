---
title: >-
  VLSI-2021 A 24–31 GHz Reference Oversampling ADPLL Achieving FoMjitter−N of
  -269.3 dB
toc: true
tags:
  - VLSI
  - 2021
  - UCD
  - PLL
abbrlink: 34443
date: 2023-03-10 00:58:54
---

![Keypoints](https://api2.mubu.com/v3/document_image/edbc6cf1-2573-49ae-ac14-0ffbeac7c81d-216525.jpg) \

##### Full Citation

J. Du et al., "**A 24–31 GHz Reference Oversampling ADPLL Achieving FoMjitter−N of -269.3 dB**," 2021 Symposium on VLSI Circuits, Kyoto, Japan, 2021, pp. 1-2, doi: 10.23919/VLSICircuits52068.2021.9492340.

[IEEE Link](https://ieeexplore.ieee.org/document/9492340) \

## Keypoints

- 4× reference oversampling (ROS)
  - bottom-plate samples at pi/4
    preset, TnH, reset to vcm
  - 2 bootstarpped SWs working alternately
  - sign is corrected in the digital domain
- fractional-N operation with two capacitive DACs
  - single-path detector assisted by the DACs
  - preset the dc voltage frac-N operation
  - LuT to translate sinusoid waveform to voltage by DAC
  - amplify PD output by 2-stage Gm then digitized by SAR ADC
- zeroed out mismatches in digital domain
  - pattern based error extraction
    - diff offset, amp , and the P/N gain mismatches
    - unbalanced edges
    - ref diff mismatch
  - coarsely calibrated by DAC
  - 4-tap moving average (MA) remove fine residue
- class-F23 DCO
  - 3HE
  - LT filters out the fundamental harmonic current

## Background

- lowering N to suppress noise from phase detectors
  - expensive high-frequency (>200 MHz) reference
  - high power reference multiplier with duty-cycle calibration
  - cascaded PLL
- eliminate high power mm-wave frequency dividers
  - sub-sampling PLL
  - injection locked
  - need FLL for freq tracking

<img src="https://api2.mubu.com/v3/document_image/979dc502-4382-49fb-a0c1-90759e7f5e9b-216525.jpg" width = "500" alt="Block diagram of the proposed mm-wave reference-oversampling ADPLL with details of digital implementation" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  50 MHz \
**OUT**  24 - 31 GHz \
**REF SPUR**  -65 dBc \
**FRAC SPUR**  -40 dBc \
**POWER**  11.9 mW  \
**RMS JITTER**  237 fs \
**FOM**  -241.7 dB \

## Important References

> *bottom-plate over-sampling with a zero-forcing technique* \
> [6] J. Du, T. Siriburanon, Y. Hu, V. Govindaraj and R. B. Staszewski, "A 2.02–2.87-GHz −249-dB FoM 1.1-mW Digital PLL Exploiting Reference-Sampling Phase Detector," in IEEE Solid-State Circuits Letters, vol. 3, pp. 158-161, 2020, doi: 10.1109/LSSC.2020.3008298.
> 
> *uses a large array of ac-coupled switches and detectors* \
> [7] J. -H. Seol, D. Sylvester, D. Blaauw and T. Jang, "A Reference Oversampling Digital Phase-Locked Loop with -240 dB FOM and -80 dBc Reference Spur," 2019 Symposium on VLSI Circuits, Kyoto, Japan, 2019, pp. C160-C161, doi: 10.23919/VLSIC.2019.8778010.
