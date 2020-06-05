---
title: JSSC-2020 An Energy-Efficient Comparator With Dynamic Floating Inverter
  Amplifier
toc: true
tags:
  - JSSC
  - 2020
  - CMP
  - UTAustin
abbrlink: 64667
date: 2020-04-26 22:50:45
---

![Keypoints](https://img.mubu.com/document_image/9eb8e6d4-1b25-4804-ad7e-8432158900f0-216525.jpg) \

##### Full Citation

X. Tang et al., "An Energy-Efficient Comparator With Dynamic Floating Inverter Amplifier," in IEEE Journal of Solid-State Circuits, vol. 55, no. 4, pp. 1011-1022, April 2020. \
[IEEE Link](https://ieeexplore.ieee.org/document/8947992) \

## Keypoints

- floating-inverter pre-amplifier
  - powered by by a reservoir capacitor
  - benefits
    - reduce PVT and input common mode sensitivity
    - dynamic biased
      - reuse current
      - boost g_m/I_D
      - reduce noise

## Background

- comparator requirements
  - power efficiency
    - limited by charging the integration capacitor
  - common-mode insensitivity
    - limited by tail transisitor in linear region
- conventional approach
  - dynamic comparator
    - dynamic pre-amplifier
    - latch
    - typical: strong-arm (SA) latch
      - embedded dynamic pre-amplifer
      - regenerative latch
      - large integration capacitors C_X
        - low-noise design
        - limit energy efficiency
    - improvements
      - dynamically biased (DB) integration [12]  
        3x energy efficiency improvement
      - cascade-input [1]  
        2x energy efficiency improvement
      - bi-directional integration to reuse current [13]  
        1.5x energy efficiency improvement
      - gain-boosted comparator [4]
- Review of prior works
  - SA Latch
  - dynamically biased (DB) integration

## Proposed

- dynamic comparator
  - floating inverter amplifier (FIA)  
    7x energy efficiency improvement; CMOS DB Integration Pre-Amplifier
    - powered by a reservoir capacitor
    - isolated power domian
    - amplification independent of the input common-mode voltage
    - constant output common mode
    - dynamic source degeneration increasing gm/I_D
    - prevent full discharge of the integration capacitors
  - benefits
    - high power efficiency
    - insensitive to supply and input common-mode
    - low noise

## Details

- **Principle**
  - **CMOS DB Integration Pre-Amplifier**
    - decreased overdrive voltage of the input pair
      - increase the gm/I_D average by over 2.5 times
    - constant common-mode at nominal corner
      - avoid gain degradation
      - prevent full discharge of C_X
    - risk of common-mode drift at other corner
  - **Floating Inverter Pre-Amplifier With Reservoir Capacitor**
    - merging the two tail capacitors C_TAIL into single floating reservoir capacitor C_RES
    - reduce capacitance size
    - isolated power domain
    - constant output common-mode
    - input common-mode insensitivity
      - isolated voltage domain will be automatically shifted to balance the nMOS and pMOS overdrive voltages
  - Gain analysis
    ![Gain](https://img.mubu.com/document_image/f68b7b6a-7f8a-44c6-b5f4-52873e0cf1a8-216525.jpg)
  - Noise analysis
    ![Noise](https://img.mubu.com/document_image/287f98c1-9de5-43c8-910a-d619a473a940-216525.jpg)
  - Energy efficiency analysis
    - FoM definition
      ![FoM definiton](https://img.mubu.com/document_image/0ab66a44-a21b-4da7-b5ee-cae3cd79fe44-216525.jpg)
    - SA FoM
      ![SA FoM](https://img.mubu.com/document_image/f12d1e68-ba6c-4d35-9da3-529f5fe8e925-216525.jpg)
    - FIA pre-amplifier FoM
      ![FIA FoM](https://img.mubu.com/document_image/46e55672-350e-4c98-8c9f-a9229cd0a5f2-216525.jpg)
    - FIA advantages from
      - avoidance of unnecessary full discharge (VDD/VTHN)
      - increase gm/I_D
      - higher gain
      - improvement
        ![FoM Improvement](https://img.mubu.com/document_image/cb8d4e95-33f9-4275-b51c-83bec4ae9b81-216525.jpg)
  - Parasitic capacitance impact
    - induced common-mode rejection degradation
      ![Parasitic C](https://img.mubu.com/document_image/9d0043f8-c9d5-41db-a010-d9d45612c01d-216525.jpg)
- **Operation**
  - integration phase
    - voltage difference between source nodes decreases
    - only the differential charge is integrated on the loading capacitors
    - the common-mode voltage stays constant
  - reset phase
    - C_RES is pre-charged to VDD/GND
    - pre-amplifier output VX+/VX− is reset to VCM = VDD/2
    - VCM only needs to replenish the charge loss caused by the output common-mode shift
  - resolving
    - once the SA latch resolves, the FIA is disabled to prevent the further discharge
- **Implementation**
  - FIA stage
    - chooseing C_RES
      - large C_RES
        - fast preamplification
        - weak degradation of gm/I_D boost
        - large area
      - small C_RES
        - worse kick-back noise
        - insuffiecnt gain
  - standard SA latch

![Schematic](https://img.mubu.com/document_image/0a6696ca-7598-4fc8-8dbb-872342890f73-216525.jpg) \

![Model](https://img.mubu.com/document_image/bfa51c2e-4e3a-4512-ab38-da7f50145023-216525.jpg) ![Opeation](https://img.mubu.com/document_image/3260d0af-894a-4831-8d59-76fb6d25d9b1-216525.jpg) \

## Conclusion

**TECH** 180nm \
**ENERGY** 0.98 pJ@1.2V \
**NOISE** 46 uV \
**FOM** 2.07 nJ·uV^2 \

## Important Reference
>
> *Conference Paper (VLSI 2019)*
>
> - [14] X. Tang, B. Kasap, L. Shen, X. Yang, W. Shi, and N. Sun, “An energyefficient comparator with dynamic floating inverter pre-amplifier,” in Proc. IEEE Symp. VLSI Circuits (VLSI), Jun. 2019, pp. C140–C141. \
>
> *dynamically biased (DB) integration*
>
> - [12] H. S. Bindra, C. E. Lokin, D. Schinkel, A.-J. Annema, and B. Nauta, “A 1.2-V dynamic bias latch-type comparator in 65-nm CMOS with 0.4-mV input noise,” IEEE J. Solid-State Circuits, vol. 53, no. 7, pp. 1902–1912, Jul. 2018. \
