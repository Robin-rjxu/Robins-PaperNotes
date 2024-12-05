---
title: >-
  ESSERC-2024 A 2.5mW Fully-Passive 2nd-Order Noise-Shaping Bang-Bang PLL with
  Adaptive DCO Gain Controller Achieving 305-fsrms Jitter and –246.3 dB FoM
toc: true
tags:
  - ESSERC
  - 2024
  - BBPD
  - DPLL
  - BUT
abbrlink: 55534
date: 2024-12-05 07:52:58
---

![Keypoints](https://s21.ax1x.com/2024/12/05/pAobfe0.png) \

##### Full Citation

Z. Yuan et al., "**A 2.5mW Fully-Passive 2nd-Order Noise-Shaping Bang-Bang PLL with Adaptive DCO Gain Controller Achieving 305-fsrms Jitter and –246.3 dB FoM**," 2024 IEEE European Solid-State Electronics Research Conference (ESSERC), Bruges, Belgium, 2024, pp. 109-112, doi: 10.1109/ESSERC62670.2024.10719475.

[IEEE Link](https://ieeexplore.ieee.org/document/10719475) \

## Keypoints

- noise shaping phase detector (NSPD)
  - fully-passive second-order charge-domain 
    - principle
      - residual phase error of the prev. is converted to a voltage
      - combined with the sampled voltage of the cur.
      - resulting signal is quantized by a 1-bit comparator
      - the cur. PD output is fed back to the delta modulation path
      - 
    - circuits
      - all-passive IIR filter
      - timing
        - non-overlapped clocks
        - control by multiplexing the MMD
        - instead of the delay circuits
        - low latency with output 1/4 Tref
        - 
      - sigma stage
        - sampled voltage on Cs
        - redistribute with Cres1 and Cres2  in sequence
        - store the residual on Cres1 and Cres2
      - sampling and delta stage
        - the rising edge of the MMD output clock DIV[n:0]
        - sample and hold the reference differential sinusoid
        - store the voltage on the top-plate of Cs
      - adjustable current steering charge pump
      - 3-input comparator
        - dynamic strong-arm
        - compensate for the attenuation from the multiple redistributions
        - sizing according to adjust comparison gain
      - capacitor ratio to achieve NTF and save power
    - charge domain delta modulation
      - residual voltage from charging and discharging the Cs top-plate
      - for a fixed time using a adjustable charge pump
      - no overload
  - 1-bit dynamic comparator
  - IIR low-pass filter
    - prevent the high-freq. QN from the NSPD affecting the loop
    - better when cut-off freq ~= BW of the NSPD NTF
  - automatic DCO gain control (ADGC)
    - optimal BW to equal the PN frm the NSPD and the DCO
    - symbolic Least-Mean-Squares (LMS) algorithm
      - digital circuits
      - time domain
      - automatically controls the DCO gain
      - controllable gain K
      - settled with accumulation of correlation of delayed PD outputs
      - DSM
    - circuits
      - resistive loaded complementary class-B DCO
      - change least significant bit only
      - BW control by modifying the LSB action time
- NS-BBPLL
  - ref (differential sinewave signal ) sampling
  - second-order NSPD
  - digital loop filter (DLF)
  - multi-modulus divider (MMD)

## Background

- Internet of Things (Iot) technology
  - operating in the sub-6 GHz band
  - transceiver core modules
  - high-performance and low-power PLLs
- Bang-bang PLLs
  - small area, high gain and simple design
  - in-band noise limited by quantization noise
  - loop gain also affects the phase discrimination effect
- BBPLLs with noise shaping technique
  - effectively reduce the quantization noise of the BBPD
  - improve the equivalent resolution
  - previous works
    - first order
      - time and charge domain
      - redistribution coefficients on the NTF limits performance
    - third-order
      - time domain
      - 1.5-bit phase detector provides redundancy
      - mulitiple DTC for delta operation
  - challenging loop band width control
    - proportional gain coefficient in the digital filter
    - automatically adjusted to ensure the optimum bandwidth
    - frequency tuning size affects the BW adjustment

<img src="https://s21.ax1x.com/2024/12/05/pAobRLq.png" width = "500" alt="block diagram of the proposed NS-BBPLL" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pAob2yn.png" width = "500" alt="the proposed half fully-passive second-order NSPD" align=center />

<img src="https://s21.ax1x.com/2024/12/05/pAobgQs.png" width = "500" alt="the proposed ADGC and DCO" align=center />

## Conclusion

**TECH**  65 nm \
**REF** 50 MHz \
**OUT**  4.2 ~ 5.8 GHz \
**REF SPUR**  -48 dBc \
**POWER**  2.5 mW  \
**RMS JITTER**  305 fs \
**FOM**  -246.3 dB \

## Important References

> *BBPLLs* \
> [1] S. M. Dartizio et al., "A 12.9-to-15.1-GHz Digital PLL Based on a Bang-Bang Phase Detector With Adaptively Optimized Noise Shaping," in IEEE Journal of Solid-State Circuits, vol. 57, no. 6, pp. 1723-1735, June 2022. (first-order time-domain and charge-domain noise shaping) \
> [2] Y. Wu, P. Lu and R. B. Staszewski, "A Time-Domain 147fsrms 2.5- MHz Bandwidth Two-Step Flash-MASH 1-1-1 Time-to-Digital Converter With Third-Order Noise-Shaping and Mismatch Correction," in IEEE Transactions on Circuits and Systems I: Regular Papers, vol. 67, no. 8, pp. 2532-2545, Aug. 2020. (third-order time-domain NSPD) \
> [3] T. -K. Kuan and S. -I. Liu, "A Bang Bang Phase-Locked Loop Using Automatic Loop Gain Control and Loop Latency Reduction Techniques," in IEEE Journal of Solid-State Circuits, vol. 51, no. 4, pp. 82*1-831, April 2016. (adjust prop. gain in DLF to control BW)
> 
> *MMD output multi-phase square waves with 50% duty cycle* \
> [4] H. Liu, W. Deng, H. Jia, S. Zhang, S. Sun and B. Chi, "A 4.8-GHz Time-Interleaved Multi-Reference PLL with 16.1-fs Jitter," ESSCIRC 2023- IEEE 49th European Solid State Circuits Conference (ESSCIRC), Lisbon, Portugal, 2023, pp. 261-264.
> 
> *digital PLLs* \
> [5] H. Liu et al., "A 4.7GHz Synchronized-Multi-Reference PLL with In-Band Phase Noise Lower than Reference Phase Noise +20logNdiv ," ESSCIRC 2022- IEEE 48th European Solid State Circuits Conference (ESSCIRC), Milan, Italy, 2022, pp. 233-236. \
> [6] F. Buccoleri et al., "A 9GHz 72fs-Total-lntegrated-Jitter Fractional-N Digital PLL with Calibrated Frequency Quadrupler," 2022 IEEE Custom Integrated Circuits Conference (CICC), Newport Beach, CA, USA, 2022, pp. 1-2. \
> [7] Y. Chen, J. Gong, R. B. Staszewski and M. Babaie, "A Fractional-N Digitally Intensive PLL Achieving 428-fs Jitter and <−54-dBc Spurs Under 50-mVpp Supply Ripple," in IEEE Journal of Solid-State Circuits, vol. 57, no. 6, pp. 1749-1764, June 2022