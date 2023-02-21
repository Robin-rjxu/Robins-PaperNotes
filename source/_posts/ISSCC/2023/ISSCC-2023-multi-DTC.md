---
title: >-
  ISSCC-2023 A 9.25GHz Digital PLL with Fractional-Spur Cancellation Based on a
  Multi-DTC Topology
toc: true
tags:
  - ISSCC
  - 2023
  - Polimi
  - PLL
  - DTC
abbrlink: 53542
date: 2023-02-21 23:46:43
---

![Keypoints](https://api2.mubu.com/v3/document_image/f543c611-b42e-43ce-a23c-c0f961808b55-216525.jpg) \

## Full Citation

Giacomo Castoro, et al, "**A 9.25GHz Digital PLL with Fractional-Spur Cancellation Based on a Multi-DTC Topology**,"

## Keypoints

- random noise is random and scaled down by averaging
- frac spurs are related to QE sequence
  - combine multiple phase-shift phases of QE
  - QE harmonics are cancelled expect its N-th multiples
- implementation
  - shift QE requires shift BBPD input pairs
  - REF delay is compensated by fixed and varied terms
    - varied terms : multi-phase DIV output
      (retimed by DCO output)
    - constant terms : aux DTCs
  - aux DTC and each of main DTC are gain calibrated

## Background

- DTC nonlinearity causes quantization error
  - fractional spurs
  - increase in-band noise
- digital calibration for DTC NL
  - cost much hardware
  - long convergence time
  - dithering introduce extra noise


<img src="https://api2.mubu.com/v3/document_image/7b0c3d5a-bacd-46ff-87b6-9978205e008e-216525.jpg" width = "500" alt="The multi-DTC topology based on the phase-shifted QE cancenllation" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  250 MHz \
**OUT**  9.25 - 10.75 GHz \
**REF SPUR**  -71.1 dBc \
**FRAC SPUR**  -60.3 dBc \
**POWER**  17.9 mW \
**RMS JITTER**  69.9 fs \
**FOM**  -250.6 dB \

## Important References

> *increasing hardware resources* \
> [3] D. Cherniak et al., “A 15.6-18.2 GHz Digital Bang-Bang PLL with −63dBc in-Band Fractional Spur,” IEEE RFIC, pp. 36-39, June 2018.
>
> *long convergence times* \
> [4] C.-R. Ho and M. Chen, ”A Digital PLL with Feedforward Multi-Tone Spur Cancelation Loop Achieving <−73dBc Fractional Spur and <−110dBc Reference Spur in 65nm CMOS,” ISSCC, pp. 190-191, Feb. 2016. \
> 
> *dithering and increase in-band PN* \
> [5] E. Familier and I. Galton, “Second and Third-Order Successive Requantizers for Spurious Tone Reduction in Low-Noise Fractional-N PLLs,” IEEE CICC, pp. 1-4, May 2017. \
> [6] T. Seong et al., “A −58dBc-Worst-Fractional-Spur and −234dB-FoMjitter, 5.5GHz Ring-DCO-Based Fractional-N  PLL Using a Time-Invariant-Probability Modulator, Generating a Nonlinearity-Robust DTC-Control Word,” ISSCC, pp. 270-271, Feb. 2020.

