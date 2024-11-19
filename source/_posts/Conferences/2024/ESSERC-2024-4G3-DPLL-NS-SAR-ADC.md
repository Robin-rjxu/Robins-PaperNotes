---
title: >-
  ESSERC-2024 A 4.3 GHz Digital-Sampling PLL with Noise-Shaping SAR ADC Phase
  Detector
toc: true
tags:
  - ESSERC
  - 2024
  - DPLL
  - SPD
  - ADC
  - SAR
  - DSM
  - Umi
abbrlink: 54193
date: 2024-11-19 18:43:48
---

![Keypoints](https://s21.ax1x.com/2024/11/19/pAWeeHJ.png) \

Full Citation
M. R. Belz, Z. Xu, H. -W. Chen, S. Song and M. P. Flynn, "**A 4.3 GHz Digital-Sampling PLL with Noise-Shaping SAR ADC Phase Detector**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 105-108, doi: 10.1109/ESSERC62670.2024.10719439.

[IEEE Link](https://ieeexplore.ieee.org/document/10719439) \

## Keypoints

- noise shaping SAR ADC based PD
  - 5b quantizer
  - Delta-Sigma Modulation (DSM) based ADCs
  - high signal-to-noise ratio (SNR)
  - 2nd-order noise shaping
    - quantization noise
    - comparator noise
  - benefits
    - reduce in-band noise
    - does not need analog integrators or resonators
    - reduce effort for CDAC routing and matching
    - robust with two first-order loops
  - Cascade Noise Shaping (CaNS) 
    - 2nd order NTF
      - two 1st-order loops
      - avoid residue amplifier noise amplification
      - reducing the input-referred noise by 5x
    - EF + CIFF
      - non-resetting capacitor
      - eliminating additional kT/C
    - residue voltage is amplified by 4.5x
- DPLL with NS-SAR-ADC based PD
  - TVC
    - constant slope and sampled by DIV
    - complimentary linear ramps
    - effective time resolution of 82 fs/bit
  - DLF with first-order IIR filter
  - DCO
    - 7b R2R DAC and analog VCO
      - constant output resistance
      - form the RC low-pass filtering
    - 1st-order DSM
    - PMOS current mirror in supply
    - common mode resonator
  - retimed DIV
  - REF
    - reduce power requirement
    - clocks ADC and other digital components
    - small loading
    - less sensitive to ref slope

## Background

- ultra-low-jitter PLLs
  - increasing data rate of wireless transceivers
  - stringent EVM requirements
- challenges from DPLLs
  - time resolution of the digital PD
    - voltage domain PD
    - digitized with an ADC
    - quantization error dominates the in-band noise
    - \>8b quantizer is required
  - ADC-based PD
    - high-resolution SAR ADC
      - power efficient 
      - compact
      - expensive in power from
        - comparator noise
        - sampling KT/C noise
    - steep slope generators
      - reduce linear locking range
      - often require calibration
    - noise-shaping TDCs
  - time-based noise shaping TDC
    - reduce in-band noise
    - limited to 1st-order noise shaping
    - off-state leakage
    - charge injection
    - worse as technology scales
  - noise shaping BBPDs
    - good jitter performance
    - extensive digital calibration
    - limited 1-st order noise shaping

<img src="https://s21.ax1x.com/2024/11/19/pAWeVuF.png" width = "500" alt="Overall architecture of the PLL with NS-SAR PD" align=center />

<img src="https://s21.ax1x.com/2024/11/19/pAWeZB4.png" width = "500" alt="Implementation of the the NS-SAR ADC" align=center />

## Conclusion

**TECH**  28 nm \
**REF**  134 MHz \
**OUT**  4.3 GHz \
**REF SPUR**  -68 dBc \
**POWER**  13.7 mW  \
**RMS JITTER**  133 fs \
**FOM**  -246.2 dB \

## Important References

> *SAR ADC based PLLs* \
> [1] X. Gao et al., "9.6 A 2.7-to-4.3GHz, 0.16psrms Jjitter, −246.8dB-FOM, digital fractional-N sampling PLL in 28nm CMOS,"2016 IEEE International Solid-State Circuits Conference (ISSCC), San Francisco, CA, USA, 2016, pp. 174-175 \
> [2] J. Du, T. Siriburanon, Y. Hu, V. Govindaraj, and R. B. Staszewski, “A Reference-Waveform Oversampling Technique in a Fractional-N ADPLL,” IEEE J. Solid-State Circuits, vol. 56, pp. 3445–3457, Nov. 2021. \
> [3] Z. -Z. Chen et al., "14.9 Sub-sampling all-digital fractional-N frequency synthesizer with −111dBc/Hz in-band phase noise and an FOM of −242dB,"2015 IEEE International Solid-State Circuits Conference - (ISSCC) Digest of Technical Papers, San Francisco, CA, USA, 2015, pp.1-3
> 
> *steep slope generator* \
> [4] T. Siriburanon et al., "A 2.2 GHz -242 dB-FOM 4.2 mW ADC-PLL Using Digital Sub-Sampling Architecture," in IEEE J.Solid-State Circuits, vol. 51, no. 6, pp. 1385-1397, June 2016
> 
> *time-based noise shaping TDC GRO* \
> [5] C.-M. Hsu, M. Z. Straayer, and M. H. Perrott, “A Low-Noise Wide-BW 3.6-GHz Digital ∆Σ Fractional-N Frequency Synthesizer With a Noise-Shaping Time-to-Digital Converter and Quantization Noise Cancellation,” IEEE J. Solid-State Circuits, vol. 43, no. 12, pp. 2776–2786,2008.
> 
> *extensive digital calibration* \
> [6] S. M. Dartizio et al., “A 12.9-to-15.1-GHz Digital PLL Based on a Bang-Bang Phase Detector With Adaptively Optimized Noise Shaping,” IEEE J. Solid-State Circuits, vol. 57, no. 6, pp. 1723–1735, 2022.
> 
> *high-power analog integrator* \
> [7] M. B. Dayanik and M. P. Flynn, “Digital Fractional-N PLLs based on a Continuous-Time Third-Order Noise-Shaping Time-to-Digital Converter for a 240-GHz FMCW Radar System,” IEEE J. Solid-State Circuits, vol. 53, pp. 1719–1730, Jun. 2018.
> 
> *high-order modulation loop* \
> [8] L. Jie, B. Zheng, H.-W. Chen, and M. P. Flynn, “A Cascaded Noise-Shaping SAR Architecture for Robust Order Extension,” IEEE J. Solid-State Circuits, vol. 55, no. 12, pp. 3236–3247, 2020.
> 
> *DCO* \
> [9] M. Ferriss and M. P. Flynn, “A 14mW Fractional-N PLL Modulator with an Enhanced Digital Phase Detector and Frequency Switching Scheme,” in 2007 IEEE International Solid-State Circuits Conference. Digest of Technical Papers, 2007, pp. 352–608.
> 
> *retimed DIV* \
> [10] D. Tasca, M. Zanuso, S. Levantino, and C. Samori, “An Automatic Retiming System for Asynchronous Fractional Frequency Dividers,” in 6th Conference on Ph.D. Research in Microelectronics & Electronics, Berlin, Germany, Jul. 2010, pp. 1–4.
> 
> *large capacitive load in reference sampling architecture *\
> [11] J. Sharma and H. Krishnaswamy, “A 2.4-GHz Reference-Sampling Phase-Locked Loop That Simultaneously Achieves Low-Noise and Low-Spur Performance,” IEEE J. Solid-State Circuits, vol. 54, no. 5, pp. 1407–1424, 2019.
> 
> *noise shaping NTF* \
> [12] H.-W. Chen, S. Lee, and M. Flynn, “A 0.024mm² 84.2dB-SNDR 1MHz-BW 3rd-Order VCO-Based CTDSM with NS-SAR Quantizer (NSQ VCO CTDSM),” in 2023 IEEE Symposium on VLSI Technology and Circuits, 2023, pp. 1–2.
> 
> *common-mode resonator in VCO * \
> [13] M. Garampazzi, P. M. Mendes, N. Codega, D. Manstretta, and R. Castello, “Analysis and Design of a 195.6 dBc/Hz Peak FoM P-N Class-B Oscillator With Transformer-Based Tail Filtering,” IEEE J. Solid-State Circuits, vol. 50, no. 7, pp. 1657–1668, 2015.
> 
> *NMOS  digitally-switched unit capacitor * \
> [14] B. Hershberg, K. Raczkowski, K. Vaesen, and J. Craninckx, “A 9.1–12.7 GHz VCO in 28nm CMOS with a Bottom-Pinning Bias Technique for Digital Varactor Stress Reduction,” in ESSCIRC 2014, 2014, pp. 83–86.
> 
> [15] Y. Wu, M. Shahmohammadi, Y. Chen, P. Lu and R. B. Staszewski, "A 3.5–6.8-GHz Wide-Bandwidth DTC-Assisted Fractional-N All-Digital PLL With a MASH ΔΣ-TDC for Low In-Band Phase Noise," in IEEE J. of Solid-State Circuits, vol. 52, no. 7, pp. 1885-1903, July 2017