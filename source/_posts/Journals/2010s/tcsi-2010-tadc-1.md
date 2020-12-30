---
title: Stochastic Flash Analog-to-Digital Conversion
toc: true
tags:
  - ADC
  - TCSI
  - 2010
  - OSU
abbrlink: 39086
date: 2020-08-20 15:12:45
---
#### Citation

S. Weaver, B. Hershberg, P. Kurahashi, D. Knierim and U. Moon, "Stochastic Flash Analog-to-Digital Conversion," in IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 57, no. 11, pp. 2825-2833, Nov. 2010, doi: 10.1109/TCSI.2010.2050225. [IEEE Link](https://ieeexplore.ieee.org/document/5491110) \

## Keypoints

![Keypoints](https://api2.mubu.com/v3/document_image/f3fd1885-537f-4af9-9712-2fd0ff4c2b54-216525.jpg) \

## Notes

- introduction
  - standard flash ADC
    - uses a resistor string to set individual comparator trip points
  - stochastic flash ADC
    - uses random comparator offset to set the trip points
    - Comparator trip points follow Gaussian CDF
- theoretical stochastic ADC
  - basic architecture
    - a group of comparators with random offsets
    - followed by a ones adder
  - principles
    - comparator offset follows Gaussian distribution
    - the ADC voltage transfer function is the CDF of the random comparator offset
    - overall input referred noise of the ADC is not limited by the noise of single comparator
  - required number of comparators: n ≈ 2· 4^N
  - non-ideality
    - The actual distribution of comparator thresholds is not uniform
    - but rather a Gaussian distribution
  - solution
    - using two basic stochastic flash ADCs
    - each with a Gaussian CDF transfer function but with a different means
  - maximum achievable number of bits (MANOB) limited to 8.97 bits

- implementation
  - two separate groups of comparators
  - adjust means to be ± 1.078 σ
  - 3840 comparators in each group
  - 20 subgroups of 192 comparators
    - can be independently enable/disable
    - study the effect of the comparator number
  - pipelined Wallace tree ones adder
  - measured σ = 140 mV
  - input signal range 280 mV
  - 8.5-dB improvement by dividing to 2 groups
  - the input-referred noise
    - decreases as the number of comparators increases
    - due to an averaging effect of the noise

## Figures

![principle of the stochastic ADC](https://api2.mubu.com/v3/document_image/5b1788bf-2180-4c9d-b254-666a56cae2c4-216525.jpg) \

![linearization by group splitting](https://api2.mubu.com/v3/document_image/fa5910df-7347-40bb-ade2-e12f431dab1e-216525.jpg) \

## Conclusion

**Technology** 0.18 um CMOS \

**Resolution** 6b \

**Speed** 18 MS/s \

**Input Range** 140 mV \

**SFDR** 42.86 dB \

**SNDR** 33.59 dB \

**DNL/INL** 0.5/1.07 LSB \

**Power** 631 uW \

**Area** 0.43 mm^2 \

## References
>*first propose stochastic ADC*
> 
> - \[5\] J. L. Ceballos, I. Galton, and G. C. Temes, “Stochastic analog-to-digital conversion,” in Proc. 48th Midwest Symp. Circuits Syst., 2005, pp. 855–858. \
> 
> *choose comparator with desired offsets*
> 
> - \[6\] D. C. Daly and A. P. Chandrakasan, “A 6 b 0.2-to-0.9 V highly digital flash ADC with comparator redundancy,” IEEE J. Solid-State Circuits, vol. 44, no. 11, pp. 3030–3038, Nov. 2009. \
> 
> *only the best of redundant comparators*
> 
> - \[7\] C. Donovan and M. P. Flynn, “A “digital” 6-bit ADC in 0.25- m CMOS,” IEEE J. Solid-State Circuits, vol. 37, no. 3, pp. 432–437, Mar. 2002. \