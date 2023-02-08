---
title: >-
  VLSI-2020 Model Predictive Control of an Integrated Buck Converter for Digital
  SoC Domains in 65nm CMOS
toc: true
tags:
  - VLSI
  - 2020
  - Power
  - UW
abbrlink: 3864
date: 2020-08-12 12:47:28
---

#### Citation

Model Predictive Control of an Integrated Buck Converter for Digital SoC Domains in 65nm CMOS

## Keypoints

![Keypoints](https://api2.mubu.com/v3/document_image/f30f0979-29d3-48ad-ba50-8b4420d23fab-216525.jpg)

## Notes

- target
  - minimize peak Vdd droop → adaptive clocking
  - minimize time τ_settle to restore Vdd to a reference Vref
- previous works for reduce τ_settle
  - Proportional Integral Differential (PID) control
    - classic, widely adopted, popular
  - Time-Optimal Control (TOC)
    - stability analysis challenges
    - only for load-step current
  - Model Predictive Control (MPC)
    - stable and optimal response under random disturbances
    - large computational latency
- proposed MPC
  - 2-cycle trajectory prediction
  - deal with duty-cycle saturation
    - process: maximally slew I_L; slew I_L back to I_load at n_Imax; I_L=I_load at n_Imatch
    - timing n_Imax for minimal τ_settle
    - charge Qs tracking: Qs = v_err · CL = Δi_n^2\[n_Imax\] · L/(2V_ref)
  - optimized dataflow
    - only d\[n\] is computed in cycle n, no calculate d\[n+1\]
    - migrating computations away from the critical path between Vdd\[n\] and d\[n\]

## Conclusion

**Vin**   1.8 V \

**Vout **  0.6-1.0 V \

**Max I_load**   400 mA \

**L**   1 uH \

**C_L**   1 uF \

**F_sw**   10MHz \

**Peak Efficiency**   91.9% \

**Vout droop**   37.5 mV@191 mA/0.12 ns \

**Settling Time**   550 ns \

## Figures

![system overview](https://api2.mubu.com/v3/document_image/d4da06ed-49d5-4f14-8d75-1f6c0d2a75af-216525.jpg) \

![bulk model](https://api2.mubu.com/v3/document_image/5e0db805-9b4a-4380-9da0-e2c8c2a32efb-216525.jpg) \

![proposed 2-cycle MPC](https://api2.mubu.com/v3/document_image/cc833866-3d86-4421-83bd-cdd9dbfa3c01-216525.jpg) \



![response under saturation](https://api2.mubu.com/v3/document_image/85b3f5c2-da52-4c22-9032-5a48bc056f8c-216525.jpg) \

## References
>*adaptive clocking*
>
>- \[1\] K. A. Bowman et al., "A 16 nm All-Digital Auto-Calibrating Adaptive Clock Distribution for Supply Voltage Droop Tolerance Across a Wide Operating Range," in IEEE Journal of Solid-State Circuits, vol. 51, no. 1, pp. 8-17, Jan. 2016, doi: 10.1109/JSSC.2015.2473655. \
>
>- \[2\] K. Wilcox et al., "Steamroller Module and Adaptive Clocking System in 28 nm CMOS," in IEEE Journal of Solid-State Circuits, vol. 50, no. 1, pp. 24-34, Jan. 2015, doi: 10.1109/JSSC.2014.2357428.
>
>*time optimal control (TOC)*
>
>- \[3\] J. P. LaSalle, TIME OPTIMAL CONTROL SYSTEMS, Proceedings of the National Academy of Sciences Apr 1959, 45 (4) 573-577; DOI: 10.1073/pnas.45.4.573. \
>- \[4\] Y. Li, C. Chen and C. Tsai, "A Constant On-Time Buck Converter With Analog Time-Optimized On-Time Control," in IEEE Transactions on Power Electronics, vol. 35, no. 4, pp. 3754-3765, April 2020, doi: 10.1109/TPEL.2019.2938532. \
>
>*Model Predictive Control (MPC)*
>
>- \[6\] S. Vazquez, J. Rodriguez, M. Rivera, L. G. Franquelo and M. Norambuena, "Model Predictive Control for Power Converters and Drives: Advances and Trends," in IEEE Transactions on Industrial Electronics, vol. 64, no. 2, pp. 935-947, Feb. 2017, doi: 10.1109/TIE.2016.2625238. \
>MPC theoretical analysis (stability)
>- \[8\] Carlos E. García, David M. Prett, Manfred Morari, Model predictive control: Theory and practice—A survey, Automatica, Volume 25, Issue 3, Pages 335-348, 1989, doi:10.1016/0005-1098(89)90002-2. \