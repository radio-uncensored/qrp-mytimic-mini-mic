# M9OMS MyTiMic

A compact push-to-talk electret microphone for portable SSB operating with the QRP Labs QMX / QMX+.

This repository holds **test results only**. It does not contain design files.

**Store listing:** [M9OMS MyTiMic V1](https://m9oms.com/product/mytimic_v_1-microphone/)

Independent design; not affiliated with or endorsed by any radio manufacturer.

---

## Design features

- PTT filter to suppress switching transients
- RF bypassing at the jack, with a C0G capacitor
- Stitched ground planes on both sides of the PCB
- Repairable: screw-held shell; the PTT switch, capsule and jack can be replaced

## Why the PTT filter?

Some QMX users report a false "G" (GPS protection) indication when keying up with a PTT microphone.

According to the QMX manual, the radio detects a GPS by monitoring the ring contact for 9600-baud serial data. The ring is also the microphone line.

**Working hypothesis:** when the PTT button is pressed or released, its contacts may bounce, producing fast transitions on the tip. Some of that transient energy can couple into the ring through the plug, cable or PCB, where the QMX may read it as serial data.

The MyTiMic adds a filter on the PTT line and a capacitor on the ring, both at the jack, to slow those transitions and suppress what couples across. The parts are on the microphone board, so paddle operation is unaffected.

## Results so far

| Test | Board without filter | MyTiMic | Report |
| --- | --- | --- | --- |
| Ring transient on PTT press, Mic Test mode, no RF (electret absent) | ≈ −500 mV spike on 10 of 10 presses | No capture at −24 mV trigger (10 presses) | [2026-11 PTT transient](2026-11-ptt-transient.md) |
| Ring transient on PTT press, transmitting into dummy load | ≈ −500 mV spike on 10 of 10 presses | Small RF-related capture at −24 mV; none at −50 mV | [2026-11 PTT transient](2026-11-ptt-transient.md) |

Measured on the QMX PCB, ring to sleeve. Full setup, conditions and captures are in the linked report.

The filter reduced coupled spikes on the ring below the −24 mV trigger threshold, a reduction of at least 20× (26 dB). Further testing is listed in the report.

## Compatibility

Values were chosen using the published QMX schematic from QRP Labs. Results should not be assumed to apply to other radios that use the same TRS pinout; their input circuits may differ.

## Test reports

| Date | Report |
| --- | --- |
| November 2026 | [PTT transient coupling into the ring](2026-11-ptt-transient.md) |

