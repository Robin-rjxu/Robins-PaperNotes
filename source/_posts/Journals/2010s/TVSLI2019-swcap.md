---
title: >-
  TVLSI-2019 Analysis of Bitwise and Samplewise Switched Passive Charge Sharing
  SAR ADCs
toc: true
tags:
  - ADC
  - SAR
  - UW
  - 2019
  - TVLSI
abbrlink: 10209
date: 2020-08-11 23:53:19
---

#### Citation

Analysis of Bitwise and Samplewise Switched Passive Charge Sharing SAR ADCs  
C. -. R. Shi and A. Wang, "Analysis of Bitwise and Samplewise Switched Passive Charge Sharing SAR ADCs," in IEEE Transactions on Very Large Scale Integration (VLSI) Systems, vol. 27, no. 9, pp. 1977-1989, Sept. 2019, doi: 10.1109/TVLSI.2019.2909671.  \
[IEEE Link](https://ieeexplore.ieee.org/document/8701492) \ 

## Keypoints

![Keypoints](https://api2.mubu.com/v3/document_image/493b09e5-c507-4282-ba57-a44c2c87598a-216525.jpg) \

## Notes

- **background**
  
  - passive charge sharing \[13\]
    - samplewise-switched reference reservoir (SS-RCR )
      - a large capacitor precharged to the reference voltage  as the reference for all bit switching \[15\]
    - bitwise-swithced RCR (BS-RCR)
      - a bit reference charge reservoir (RCR) with the capacitance β times larger than that of the bit weight capacitor is used to replace the reference source \[16-18\]
  - Merged capacitor switching (MCS) \[3\]
    - energy-efficient SAR-ADC bit decision method
  
- **bitwise and samplewise switched passive charge sharing SAR ADC**
  
  - remove the power-hungry buffer
  - **BS-RCR**
    - seperated RCR for each bit switching
    - the finite reservoir capacitance error appears in the form of bit weight error
    - naturally subradix-2
    - correction
      - digitally corrected precisely
      - eliminated by using a sufficiently large β
  - **SS-RCR**
    - using one sufficient large capcitor as the reference for every bit switching
    - the finite reservoir capacitance error appears is highly input dependent
    - super-radix-2 and subradix-2 properties depends on inputs
      - shows the missing-level errors
      - cannot be corrected
  
- equivalent-circuit for the analysis of passive charge sharing

- BS-RCRs have better linearity

## Figures

![BS-RCR](https://api2.mubu.com/v3/document_image/705f290a-93bf-4137-8dbe-b95bf04436ee-216525.jpg) \

![SS-RCR](https://api2.mubu.com/v3/document_image/cf471ba1-dc5e-4790-bde1-dc11d3ebbd76-216525.jpg) \

## Conclusion

- theorical analysis
- BS-RCR
  - the reference error is in the form of bit weight error
  - essentially a subradix-2
  - correction
    - digitally corrected precisely
    - eliminated by using a sufficiently large β
- SS-RCR
  - super-radix-2 and subradix-2 properties depends on inputs
  - shows the missing-level errors
  - cannot be corrected

## Important Reference

> *merged capacitors witching*
>
> - \[3\] V. Hariprasath, J. Guerber, S.-H. Lee, and U.-K. Moon, “Merged capacitor switching based SAR ADC with highest switching energyefficiency,” Electron. Lett., vol. 46, no. 9, pp. 620–621, Apr. 2010.  \ 
>
> *samplewise RCR*
>
> - \[15\] R. Kapusta, J. Shen, S. Decker, H. Li, E. Ibaragi, and H. Zhu, “A 14 b 80 MS/s SAR ADC With 73.6 dB SNDR in 65 nm CMOS,” IEEE J. Solid-State Circuits, vol. 48, no. 12, pp. 3059–3066, Dec. 2013.  \ 
>
> *bitwise RCR*
> 
> - \[16\] M. Maddox, B. Chen, M. Coln, R. Kapusta, J. Shen, and L. Fernando, “A 16 bit linear passive-charge-sharing SAR ADC in 55 nm CMOS,” in Proc. IEEE Asian Solid-State Circuits Conf. (A-SSCC), Nov. 2016, pp. 153–156.  \ 
>
> - \[17\] J. Shen et al., “A 16-bit 16-MS/s SAR ADC with on-chip calibration in 55-nm CMOS,” IEEE J. Solid-State Circuits, vol. 53, no. 4, pp. 1149–1160, 2018.  \ 
> 
> - \[18\] B. Chen, M. Maddox, M. C. W. Coln, Y. Lu, and L. D. Fernando, “Precision passive-charge-sharing SAR ADC: Analysis, design, and measurement results,” IEEE J. Solid-State Circuits, vol. 53, no. 5, pp. 1481–1492, May 2018.  \ 
