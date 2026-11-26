# Investigating PTT transients: Part 2

**M9OMS MyTiMic** · Oscilloscope measurements, November 2026 · [Back to README](README.md) · [Part 1](2026-11-ptt-transient1.md)

## Background

[Part 1](2026-11-ptt-transient1.md) demonstrated that when activating the PTT circuit, a transient couples onto the Ring.

This document examines a single variable: the effect of the TRS cable on that transient.

## Cables tested

Three cables were tested, each 1 m long:

1. **Control cable:** the same cable used in Part 1.
2. **CPC cable A:** supplied by CPC, with a published datasheet (see cable construction, below).
3. **CPC cable B:** supplied by CPC, with a published datasheet (see cable construction, below).

| Cable | Source | Construction | Length |
| --- | --- | --- | --- |
| Control | As part 1 | Consumer headphone cable; no datasheet | 1 m |
| CPC cable A | CPC | 3 twisted cores, no screen, Ø 3.0 mm | 1 m |
| CPC cable B | CPC | 2 cores, overall foil and copper screen, Ø 4.0 mm | 1 m |

## Measurement setup

All three cables were tested with the control PCB, which had no decoupling or PTT debounce components.

The method matched Test 3 of part 1: transmitting into a dummy load on 14.150 MHz by pressing the PTT button.

Again, no electret was fitted. Any transient on the Ring is due to activation of the PTT circuit, coupled through the cable.

The Ring-to-Sleeve signal was measured on the QMX PCB using an oscilloscope probe with a short ground spring. Channel 1 was set to 10×, AC coupling. The single-capture trigger was DC-coupled, on a falling edge at −50 mV.

The QMX was powered from a bench supply at 12.00 V.

## Test results 1: Control cable

An excursion of ≈ −500 mV appeared on every PTT press, matching part 1 and confirming that the measurement is repeatable.

![Control PCB with the control cable, PTT into dummy load](captures/control_cable.png)
*Control PCB, control cable. Excursion ≈ −500 mV, as in part 1.*

## Test results 2: CPC cable A

Excursion reduced by more than half, to ≈ −200 mV.

![Control PCB with CPC cable A, PTT into dummy load](captures/CABLE1.png)
*Control PCB, CPC cable A. Excursion ≈ −200 mV.*

## Test results 3: CPC cable B

Excursion reduced further, to ≈ −125 mV.

![Control PCB with CPC cable B, PTT into dummy load](captures/CABLE2.png)
*Control PCB, CPC cable B. Excursion ≈ −125 mV.*

## Cable construction

**Cable A:** three insulated cores, each 7 × 0.10 mm copper, twisted together along the length of the cable, in a 3.0 mm PVC jacket. There is no screen; the Sleeve is carried on one of the three cores.

[](captures/cable_a_section.svg)


**Cable B:** two insulated cores, each 10 × 0.10 mm copper, inside an overall screen of aluminium foil and 32 × 0.10 mm copper, in a 4.0 mm PVC jacket. The screen carries the Sleeve, surrounding both cores.

[](captures/cable_b_section.svg)

## Summary

| Cable | Excursion | Relative to control |
| --- | --- | --- |
| Control | ≈ -500 mV | — |
| CPC cable A | ≈ -200 mV | ≈ 2.4× lower (≈ 8 dB) |
| CPC cable B | ≈ -125 mV | ≈ 4× lower (≈ 12 dB) |

The choice of TRS cable affects how much of the PTT transient couples onto the Ring. None of the cables tested removed it entirely; for comparison, the MyTiMic PCB in part 1 reduced it below −24 mV.

This document covers Ring transients only. Further tests could assess other aspects of performance, such as RF interference.

Typically, TRS cables are chosen for their size, flexibility, how well they coil and how they feel in the hand. This test demonstrates that their electrical characteristics also matter. Typical consumer TRS cable do not offer data sheets - in the absence of bench testing, their impact on portable operation is therefore unknown. 

---
