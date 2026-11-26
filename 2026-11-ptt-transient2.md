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

| Cable | Source | Part number | Construction | Length |
| --- | --- | --- | --- | --- |
| Control | As part 1 | — | [TO FILL] | 1 m |
| CPC cable A | CPC | [TO FILL] | [TO FILL] | 1 m |
| CPC cable B | CPC | [TO FILL] | Figure-8, individually screened cores [TO FILL] | 1 m |

## Measurement setup

All three cables were tested with the control PCB, which had no decoupling or PTT debounce components.

The method matched Test 3 of part 1: transmitting into a dummy load on 14.150 MHz by pressing the PTT button.

Again, no electret was fitted. Any transient on the Ring is due to activation of the PTT circuit, coupled through the cable.

The Ring-to-Sleeve signal was measured on the QMX PCB using an oscilloscope probe with a short ground spring. Channel 1 was set to 10×, AC coupling. The single-capture trigger was DC-coupled, on a falling edge at −50 mV.

The QMX was powered from a bench supply at 12.00 V.

## Test results 1: Control cable

An excursion of approximately −500 mV appeared on every PTT press, matching part 1 and confirming that the measurement is repeatable.

![Control PCB with the control cable, PTT into dummy load](captures/control_cable.png)
*Control PCB, control cable. Excursion of approximately −500 mV, as in part 1.*

## Test results 2: CPC cable A

The excursion fell by more than half, to just over −200 mV.

![Control PCB with CPC cable A, PTT into dummy load](captures/CABLE1.png)
*Control PCB, CPC cable A. Excursion just over −200 mV.*

## Test results 3: CPC cable B

The excursion fell further, to approximately −125 mV.

![Control PCB with CPC cable B, PTT into dummy load](captures/CABLE2.png)
*Control PCB, CPC cable B. Excursion of approximately −125 mV.*

## Cable construction

[TO FILL: construction details from each datasheet.]

In cable B, each core has its own screen, connected to the Sleeve. A grounded screen therefore runs between the Tip and Ring conductors along the full length of the cable, reducing the capacitive coupling between them.

## Summary

| Cable | Excursion (approx.) | Relative to control |
| --- | --- | --- |
| Control | −500 mV | — |
| CPC cable A | just over −200 mV | ≈ 2.4× lower (≈ 8 dB) |
| CPC cable B | −125 mV | ≈ 4× lower (≈ 12 dB) |

The choice of TRS cable affects how much of the PTT transient couples onto the Ring. None of the cables tested removed it entirely; for comparison, the MyTiMic PCB in part 1 reduced it below −24 mV.

This document covers Ring transients only. Further tests could assess other aspects of performance, such as RF interference.

Typically, TRS cables are usually chosen for their size, flexibility, how well they coil and how they feel in the hand. This test demonstrates that their electrical characteristics also matter. Typical consumer TRS cable do not offer data sheets - in the absence of bench testing, their impact on portable operation is therefore unknown. 

---
