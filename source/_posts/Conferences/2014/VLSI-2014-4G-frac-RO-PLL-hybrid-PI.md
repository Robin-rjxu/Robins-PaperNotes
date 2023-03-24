---
title: >-
  VLSI-2014 A 4.25GHz–4.75GHz calibration-free fractional-N ring PLL using
  hybrid phase/current-mode phase interpolator with 13.2dB phase noise
  improvement
toc: true
tags:
  - ISSCC
  - 2014
  - UIUC
  - PLL
  - MDLL
abbrlink: 54924
date: 2023-03-24 22:16:45
---

![Keypoints](https://api2.mubu.com/v3/document_image/f31dde71-df06-4baf-943e-83efbb449514-216525.jpg) \

##### Full Citation

R. K. Nandwana et al., "**A 4.25GHz–4.75GHz calibration-free fractional-N ring PLL using hybrid phase/current-mode phase interpolator with 13.2dB phase noise improvement**," 2014 Symposium on VLSI Circuits Digest of Technical Papers, Honolulu, HI, USA, 2014, pp. 1-2, doi: 10.1109/VLSIC.2014.6858446.

[IEEE Link](https://ieeexplore.ieee.org/document/6858446) \

## Keypoints

- cascading a low noise intg MDLL with a frac PLL
  - MDLL : 50M -> 500M
  - frac PLL :  500M -> 4G
- hybrid phase/current-mode phase interpolator (HPC-PI)
  - XOR-PD
    - two current-mode XOR-PDs
    - digitally weighted, summed, and filtered to get Vctrl
  - HPC-PI
    - indirectly introducing phase shift
    - a charge imbalance on the PLL LPF
    - rely on high loop gain of the PLL to suppress NL
    - fine resolution without slew-rate ctrl
  - circuits
    - four XOR gates
    - two PMOS current sources
    - 4-bit current steering DAC
    - unity gain buffer to suppress Vds mismatch

## Background

- frac PLL QE cancellation
  - DAC at the CP output
  - PI at the DIV output
- conv PI
  - inherently non-linear due to V-to-Ph
  - require closely spaced phases

<img src="https://api2.mubu.com/v3/document_image/66c19736-2b42-4b3d-ba08-80bb97d289fe-216525.jpg" width = "600" alt="Simplified block diagram of the proposed fractional-N PLL" align=center />

## Conclusion

**TECH**  65 nm \
**REF**  50 MHz \
**OUT**  4.25 - 4.75 GHz \
**REF SPUR**  -60 dBc \
**POWER**  11.6 mW  @ 1V \
**RMS JITTER**  1.5 ps \
**FOM**  -225.8 dB \

## Important References

> *phase noise cancellation/suppression in frac PLL* \
> *DAC*
> [1] S. Pamarti, L. Jansson, and I. Galton, “A wideband 2.4-GHz delta-sigma fractional-N PLL with 1-Mb/s in-loop modulation,” IEEE Journal of Solid State Circuits, vol. 39, no. 1, pp. 49–62, Jan. 2004, doi: 10.1109/JSSC.2003.820858.
> 
> *phase interpolators (PI)* \
> *elaborate NL cali* \
> [2] M. Zanuso, S. Levantino, C. Samori and A. Lacaita, "A 3MHz-BW 3.6GHz digital fractional-N PLL with sub-gate-delay TDC, phase-interpolation divider, and digital mismatch cancellation," 2010 IEEE International Solid-State Circuits Conference - (ISSCC), San Francisco, CA, USA, 2010, pp. 476-477, doi: 10.1109/ISSCC.2010.5433842.
> 
> *noise-shaped segmentation techniques* \
> [3] T. -K. Kao, C. -F. Liang, H. -H. Chiu and M. Ashburn, "A wideband fractional-N ring PLL with fractional-spur suppression using spectrally shaped segmentation," 2013 IEEE International Solid-State Circuits Conference Digest of Technical Papers, San Francisco, CA, USA, 2013, pp. 416-417, doi: 10.1109/ISSCC.2013.6487795.
> 
> *wide bandwidth MDLL* \
> [4] R. Farjad-Rad et al., "A 0.2-2 GHz 12 mW multiplying DLL for low-jitter clock synthesis in highly-integrated data communication chips," 2002 IEEE International Solid-State Circuits Conference. Digest of Technical Papers (Cat. No.02CH37315), San Francisco, CA, USA, 2002, pp. 76-77 vol.1, doi: 10.1109/ISSCC.2002.992946.
> 
> *PI NL suppression in PLL* \
> [5] T. Toifl et al., "0.94ps-rms-jitter 0.016mm/sup 2/ 2.5GHz multi-phase generator PLL with 360/spl deg/ digitally programmable phase shift for 10Gb/s serial links," ISSCC. 2005 IEEE International Digest of Technical Papers. Solid-State Circuits Conference, 2005., San Francisco, CA, USA, 2005, pp. 410-607 Vol. 1, doi: 10.1109/ISSCC.2005.1494043.
