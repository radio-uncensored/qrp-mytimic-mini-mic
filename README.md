# M9OMS MyTiMic

A compact push-to-talk electret microphone for portable SSB operating with the QRP Labs QMX / QMX+.

This repository contains test results only.

**Store listing:** [M9OMS MyTiMic V1](https://m9oms.com/product/mytimic_v_1-microphone/)


---

## PCB features

- PTT filter to suppress transients from coupling onto the Ring
- RF bypassing at the jack (C0G)
- Stitched ground planes

## Why the PTT filter?

Some QMX users report a false "G" (GPS protection) indication when keying up with a PTT microphone.

The MyTiMic adds a PTT debounce and a capacitor on the ring, to slow those transitions and suppress coupling.

## Measurements so far

| Comparison | Board without filter | MyTiMic |
| --- | --- | --- |
| Ring transient on PTT press, Mic Test mode (PA inactive) | ≈ −500 mV spike on 10 of 10 presses | No capture at −24 mV trigger (10 presses) |
| Ring transient on PTT press, transmitting into dummy load | ≈ −500 mV spike on 10 of 10 presses | Small PA-related capture at −24 mV; none at −50 mV |

Measured on the QMX PCB, ring to sleeve. Full setup, conditions and captures are in the linked report.

The components reduce coupled spikes on the ring below the −24 mV trigger threshold, a reduction of at least 20× (26 dB). See below.

## Compatibility

Values were chosen using the published QMX schematic from QRP Labs. Results should not be assumed to apply to other radios that use the same TRS pinout.

## Oscilloscope measurements

| Date | Link |
| --- | --- |
| November 2026 | [Investigating PTT transients](2026-11-ptt-transient.md) |

