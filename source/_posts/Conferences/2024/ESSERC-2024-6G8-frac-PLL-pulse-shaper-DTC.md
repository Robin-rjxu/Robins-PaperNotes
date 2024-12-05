---
title: >-
  ESSERC-2024 A 6.8GHz -269.9 FOMJitter-N-Area Fractional-N Pulse Shaper Based
  PLL with Range Extension DTC
toc: true
tags:
  - ESSERC
  - 2024
  - DPLL
  - DTC
  - FDU
abbrlink: 6304
date: 2024-12-05 16:43:52
---

![Keypoints](https://s21.ax1x.com/2024/12/05/pAT1DW6.png) \

##### Full Citation

H. Gao et al., "**A 6.8GHz -269.9 FOMJitter-N-Area Fractional-N Pulse Shaper Based PLL with Range Extension DTC**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 697-700, doi: 10.1109/ESSERC62670.2024.10719470.

[IEEE Link](https://ieeexplore.ieee.org/document/10719470) \

## Keypoints

- pulse-shaped loop filter
  - tuning prop. gain by pulse width
  - multi-rate time domain modeling
  - pulse width is a × Tvco cycles \
    a=N in a traditional PLL \
  - constant loop gain
  - change prop. gain beta simultaneously
  - beta is merged into the DCO’s proportional gain
- range-extension constant-slope DTC
  - nonlinearity-cancellation
  - Range-Extension (RE)
    - MASH-1-1 requires 2 Tvco
    - pre-charging (φ1) and charge sharing (φ2)
    - Vst can be boosted above VDD
      - when a non-zero D[8:0] is applied in φ2
      - DTC output range is doubled
  - offset compensation
    - systematic error cross the upper boundary
    - adding the offset code of “1” to DTC control
    - improve linearity
- Pulse Shaper based FNPLL
  - MASH 1-1 DDSM
  - MMD
  - Pulse Generation (PG)
  - pulse-shaped loop filter
  - RE-CS-DTC
  - Vernier TDC
  - differential PI ring DCO
    - separate prop. and intg. paths
    - high prop. gain for wide BW
    - high prop./intg. gain ratio for low QN
    - fine tuning: MASH 1-1 + RDAC + RC LPF

## Background

- connectivity in chiplet applications
  - low power
  - small area
  - precise frequency tuning step
  - fractional-N phase-locked loop (FNPLL)
  - digital intensive or all-digital PLL
- ring oscillators (RO)
  - small area
  - multiple rotated phases
    - delay adjustment
    - phase interpolation
  - favor a wide bandwidth
    - poor phase noise
    - constrained by loop stability
  - type-I PLL
    - wide bandwidth
    - less stability consideration
    - high flicker noise and need additional zero
  - other structures
    - injection locking
    - feedforward phase error cancellation
    - fast phase eror correction (FPEC)
    - need FTL to suppress flicker noise
- fractional PLLs
  - MMD + DDSM
    - generate a fractional division ratio between integers
    - QN is high-pass shaped
  - DTC 
    - predicting feedback phase
    - absorb most delay difference
    - Variable-Slope (VS) 
      - adjustable load capacitors
      - the linearity is constrained by propagation delay and slope
      - improve linearity
        - adding fixed capacitor
        - more power and area
    - Constant-slope (CS)
      - linear mapping between the voltage and delay
      - mitigate linearity degradation

<img src="https://s21.ax1x.com/2024/12/05/pAT1BJx.png" width = "500" alt="System diagram of the proposed FN Pulse Shaper based ring PLL" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pAT10F1.png" width = "500" alt="DTC start voltage generation" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  76.8 MHz \
**OUT**  6.8 GHz \
**FRAC SPUR**  -53.2 dBc \
**POWER**  5.68 mW  \
**RMS JITTER**  804 fs \
**FOM**  -234.4 dB \

## Important References

> *type-I PLL* \
> [1] L. Kong and B. Razavi, "A 2.4-GHz RF Fractional-N Synthesizer With BW = 0.25fREF," IEEE Journal of Solid-State Circuits, vol. 53, no. 6, pp. 1707-1718, Jun. 2018.
> 
> *Injection Locking (IL)* \
> [2] Y. He et al., "An Injection-Locked Ring-Oscillator-Based Fractional-N Digital PLL Supporting BLE Frequency Modulation," IEEE Journal of Solid-State Circuits, vol. 57, no. 6, pp. 1765-1775, June 2022.
> 
> *Feedforward Phase-Error Cancellation (FPC)* \
> [3] Z. -H. Kang and S. -I. Liu, "A 1.6-GHz DPLL Using Feedforward Phase-Error Cancellation," IEEE Journal of Solid-State Circuits, vol. 58, no. 3, pp. 806-816, March 2023.
> 
> *Fast Phase Error Correction (FPEC)* \
> [4] Y. Lee, T. Seong, S. Yoo and J. Choi, "A Low-Jitter and Low-Reference-Spur Ring-VCO-Based Switched-Loop Filter PLL Using a Fast Phase-Error Correction Technique," IEEE Journal of Solid-State Circuits, vol. 53, no. 4, pp. 1192-1202, April 2018.
> 
> *additional fixed capacitor to imrpove DTC linearity* \
> [5] W. Wu et al., "A 28-nm 75-fsrms Analog Fractional- N Sampling PLL With a Highly Linear DTC Incorporating Background DTC Gain Calibration and Reference Clock Duty Cycle Correction," IEEE Journal of Solid-State Circuits, vol. 54, no. 5, pp. 1254-1265, May 2019, doi: 10.1109/JSSC.2019.
> 
> *constant slope DTC* \
> [6] Y. Liu, H. Gao, H. Xu, P. Lu and N. Yan, "A 10-bit 563-fs Step Constant-Slope Digital-to-Time Converter in 40-nm CMOS With Nonlinearity Cancellation and Range Extension Techniques," IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 71, no. 2, pp. 526-536, Feb. 2024.
> 
> *DCO with the switched capacitor array* \
> [7] A. Elkholy, S. Saxena, R. K. Nandwana, A. Elshazly and P. K. Hanumolu, "A 4mW wide bandwidth ring-based fractional-N DPLL with 1.9psrms integrated-jitter," 2015 IEEE Custom Integrated Circuits Conference (CICC), San Jose, CA, USA, 2015.
> 
> *multi-rate time domain modeling* \
> [8] Y. Hu, T. Siriburanon and R. B. Staszewski, "Multirate Timestamp Modeling for Ultralow-Jitter Frequency Synthesis: A Tutorial," in IEEE Transactions on Circuits and Systems II: Express Briefs, vol. 69, no. 7, pp. 3030-3036, July 2022.
> 
> *Traditional CS-DTC only has CDAC start voltage Vst below supply voltage* \
> [9] P. Chen, F. Zhang, Z. Zong, S. Hu, T. Siriburanon and R. B. Staszewski, "A 31- μ W, 148-fs Step, 9-bit Capacitor-DAC-Based Constant-Slope Digital-to-Time Converter in 28-nm CMOS," IEEE Journal of Solid-State Circuits, vol. 54, no. 11, pp. 3075-3085, Nov. 2019.
> 
> *DTC boundary nonlinearity fractional spur and noise folding* \
> [10] Y. Donnelly and M. P. Kennedy, "Prediction of Phase Noise and Spurs in a Nonlinear Fractional- N Frequency Synthesizer," in IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 66, no. 11, pp. 4108-4121, Nov. 2019.
> 
> *the phase noise of differential RO is worse than the single-ended, but great immunity to supply noise* \
> [11] A. A. Abidi, "Phase Noise and Jitter in CMOS Ring Oscillators," IEEE Journal of Solid-State Circuits, vol. 41, no. 8, pp. 1803-1816, Aug. 2006.
> 
> *compact LC based PLL* \
> [12] C. -H. Lee et al., "A 2.7 GHz to 7 GHz Fractional-N LC-PLL Utilizing Multi-Metal Layer SoC Technology in 28 nm CMOS," in IEEE Journal of Solid-State Circuits, vol. 50, no. 4, pp. 856-866, April 2015. \
> [13] C. -C. Li et al., "A Compact Transformer-Based Fractional-N ADPLL in 10-nm FinFET CMOS," IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 68, no. 5, pp. 1881-1891, May 2021.
> 
> *RO frac PLL* \
> [14] A. Elmallah, J. Zhu, A. Khashaba, K. M. Megawer, A. Elkholy and P. K. Hanumolu, "A 3.2-GHz 405 fsrms Jitter –237.2 dB FoMJIT Ring-Based Fractional-N Synthesizer," IEEE Journal of Solid-State Circuits, vol. 57, no. 3, pp. 698-708, March 2022.