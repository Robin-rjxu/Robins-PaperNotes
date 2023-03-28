---
title: ISSCC-2018
toc: true
abbrlink: 58805
date: 2023-03-29 00:16:22
tags:
---

![Keypoints](https://api2.mubu.com/v3/document_image/c7562465-5a62-48ab-98c7-d4878b76712b-216525.jpg) \

##### Full Citation

Z. Huang, B. Jiang, L. Li and H. C. Luong, "**2.3 A 4.2µs-settling-time 3rd-order 2.1GHz phase-noise-rejection PLL using a cascaded time-amplified clock-skew sub-sampling DLL**," 2016 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2016, pp. 40-41, doi: 10.1109/ISSCC.2016.7417896.

[IEEE Link](https://ieeexplore.ieee.org/document/7417896) \

## Keypoints

- PN rejection with SS-DLL
  - an integer-N PLL cascades with n-stage SS-DLL
  - SS-DLL as a 1st-order feedback loop
    - exhibits a high-pass response
    - reject PN over a wide range
    - without degraded phase margin
- 2-stage RO-based 3rd-order PLL
  - 3rd-order PN rejection at the PLL output
    - an integer-N Type-II PLL 
    - a cascaded wideband 1st-order clock-skew SS-DLL
  - clock-skew-SS PD
    - sample the retimed-DIV output
      - down-conv to ref freq
      - extend detection range
    - large detection gain
      - increase slope == reduce rise time
      - time amplifier

## Background

- reject PN and reduce freq drift techniques
  - degrade the settling time
  - type-III PLL for high low-freq loop gain
    - degrades stability
    - requires low-freq compensation zero
    - large loop filter
    - reduces the PN suppression BW
  - injection-locked (IL) PLL
    - enhances harmonics
    - but generates large reference spurs
    - race between the INJ path and the PLL path
  - conventional sub-sampling PD
    - limited detection range
    - detection gain depends on the oscillation amplitude

<img src="https://api2.mubu.com/v3/document_image/703d433f-7578-4902-a95e-ca192d3aec59-216525.jpg" width = "500" alt="Illustration of the proposed cascaded PLL concept" align=center />

## Conclusion

**TECH**  65 nm \
**REF** 67.74 MHz \
**OUT**  1.1 - 2.1 GHz \
**REF SPUR**  -45 dBc \
**POWER**  3.84 mW @ 1.2V \
**RMS JITTER**  1.05 ps \
**FOM**  -234 dB \

## Important References

> *reject PN and reduce freq drift* \
> *type-III PLL for high low-freq loop gain* \
> [1] A. Sai et al., “A Digitally Stabilized Type-III PLL Using Ring VCO with 1.01psrms Integrated Jitter in 65nm CMOS,” ISSCC Dig. Tech. Papers, pp. 248-249, Feb. 2012.
> 
> *injection-locked (IL) PLL* \
> [2] J. Lee and H. Wang, “Study of Sub-harmonically Injection-Locked PLLs,” IEEE J. Solid-State Circuits, vol. 44, no. 5, pp. 1539-1553, May. 2009.
> 
> 
> *Type-I PLLs* \
> [3] L. Kong and B. Razavi, “A 2.4GHz 4mW Inductor-less RF Synthesizer,” ISSCC Dig. Tech. Papers, pp. 450-451, Feb. 2015.
> 
> *sub-sampling PD* \
> [4] X. Gao et al., “Spur-Reduction Techniques for PLLs Using Sub-Sampling Phase Detection,” ISSCC Dig. Tech. Papers, Feb. 2010.
> 
> *time amplifier* \
> [5] S.-K. Lee et al., “A 1GHz ADPLL with a 1.25ps Minimum Resolution Sub-Exponent TDC in 0.18um CMOS,” ISSCC Dig. Tech. Papers, Feb. 2010.
