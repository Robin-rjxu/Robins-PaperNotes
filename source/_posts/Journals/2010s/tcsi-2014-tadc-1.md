---
title: >-
  TCSI-2014 Digitally Synthesized Stochastic Flash ADC Using Only Standard
  Digital Cells
toc: true
tags:
  - ADC
  - 2014
  - OSU
abbrlink: 49959
date: 2020-08-20 23:34:10
---

#### Citation

S. Weaver, B. Hershberg and U. Moon, "Digitally Synthesized Stochastic Flash ADC Using Only Standard Digital Cells," in IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 61, no. 1, pp. 84-91, Jan. 2014, doi: 10.1109/TCSI.2013.2268571. [IEEE Link](https://ieeexplore.ieee.org/document/6552224) \ 


## Keypoints

![Keypoints](https://api2.mubu.com/v3/document_image/01ce89ce-3e34-4c6b-800a-ca60e0e2c5ed-216525.jpg)

## Notes

- introduction
  - standard flash ADC: a reference is generated specifically for each comparator
  - stochastic flash ADC: uses comparators’ inherent input-referred offsets as the trip-points
- to be synthesizable
  - remove resistor ladder but use comparator offsets as virtual references
  - prefer comparator of small size 👈 3-input NAND gate
  - ones adder to build the CDF like transfer function
  - inverse function of the distribution to linearize to an uniform CDF
- NAND3 gate comparator
  - positive feedback by cross-coupling two gates
  - static SR-latch holds the output
  - inverter based buffer to reduce the memory effect
  - set_dont_touch to prevent the synthesizer from altering the comparator model
- Gaussian distribution analysis
  - the sum of the the comparator outputs follows the Gaussian CDF
  - required number of comparators ≈ 4^N (ignore DC offset)
  - linearization
    - inverse Gaussian CDF to meet uniformed distribution assumption
    - proposed: piecewise linear approximation
      - five piecewise region
      - code based: does not rely on the shift/scale of the CDF
- implementation and measurements
  - implementation
    - auto synthesis and PnR
    - difference of the parasitic capacitance: zero-mean Gaussian distribution
  - measurements
    - ramp input
    - PVT variation of the comparator
    - large input load limits input bandwidth (87 MHz)

## Figures

![the proposed stochastic ADC](https://api2.mubu.com/v3/document_image/f720ccff-93f0-4a62-b063-9870768ee168-216525.jpg)



![analog comparator made from standard digital NAND3 cells](https://api2.mubu.com/v3/document_image/829b42e9-abfc-4018-bbf9-760a77223ce7-216525.jpg)



![linearization by inverse Gaussian CDF](https://api2.mubu.com/v3/document_image/22a07250-562f-4695-9646-e4ab780f01a4-216525.jpg)

## Conclusion

**Technology** 90 nm CMOS \

**Speed** 210 MSPS \

**Input Range** 280 mVpp (differential) \

**SFDR** 41.46 dB \

**SNDR** 35.89 dB \

**Power** 34.8 mW \

**Area** 0.18 mm^2 \

## References
> first proposed stochastic ADC
> 
> - \[4\] J. Ceballos, I. Galton, and G. Temes, “Stochastic analog-to-digital conversion,” in Proc. 48th Midwest Symp. Circuits and Systems, Aug. 2005, pp. 855–858. \
> 
> requirement of the comparator
> 
> - \[14\] Data Conversion Handbook. Burlington, MA, USA: Newnes, 2005, ch.2,p. 69, A. D. Inc.. \
> 
> Wallace tree
> 
> - \[15\] F. Kaess et al., “New encoding scheme for high-speed flash ADC’s,” in Proc. Int. Conf. Solid-State Integrated Circuit Tech., Jun. 1997, pp. 5–8. \