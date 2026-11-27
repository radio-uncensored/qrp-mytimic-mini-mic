# M9OMS MyTiMic

A compact microphone for the QRP Labs QMX / QMX+.

**Store listing:** [M9OMS MyTiMic V1](https://m9oms.com/product/mytimic_v_1-microphone/)


---

## PCB features

- PTT debounce filter
- RF bypass capacitor (C0G)
- Stitched ground planes

## Why the PTT filter?

Some QMX users report a false "G" (GPS protection) indication when keying up with a PTT microphone.

This repository investigates the effectiveness of adding an RC filter to the PTT line, to reduce coupling onto the Ring. TRS cables are also compared, to show how much the cable itself contributes.

## Measurements so far

| Comparison | Board without filter | MyTiMic |
| --- | --- | --- |
| Ring transient on PTT press, Mic Test mode (PA inactive) | ≈ −500 mV excursion | No capture at −24 mV trigger (10 presses) |
| Ring transient on PTT press, transmitting into dummy load | ≈ −500 mV excursion | Small PA-related excursion at −24 mV trigger; none at −50 mV |

Full details are in Part 1 (linked below).


### TRS cables

| Cable | Construction | Ring transient, unfiltered PCB |
| --- | --- | --- |
| Consumer headphone cable | Unknown | ≈ −500 mV |
| Cable A (default) | 3 twisted cores, unscreened, Ø 3.0 mm | ≈ −200 mV (≈ 8 dB lower) |
| Cable B (screened option) | 2 cores, foil and copper screen on Sleeve, Ø 4.0 mm | ≈ −125 mV (≈ 12 dB lower) |

Full details are in Part 2 (linked below).

## Compatibility

Values were chosen using the published QMX schematic from QRP Labs. Results should not be assumed to apply to other radios that use the same TRS pinout.

## Oscilloscope measurements

| Date | Link |
| --- | --- |
| November 2026 | [Investigating PTT transients - Part 1: PCB](2026-11-ptt-transient.md) |
| November 2026 | [Investigating PTT transients - Part 2: TRS cables](2026-11-ptt-transient2.md) |

