# Ctrl ESPT

ESP32 Thing Plus controller for a BREAD stack: the G2 (BREAD v2) Loaf controller. It is archived and not carried into G3.

## Status

- **G2, `g2-r1`:** the rev-A design, ordered from JLCPCB on 2024-09-30 (commit b81ce4a) and fabricated. It is the release of this board.
- **rev.C (2026-07):** a redraw of rev-A on `main`, which addressed the design's hardware shortcomings. It was never built.
- **G3:** a stack is controlled by a Raspberry Pi, or another SBC that meets the requirements, driving the Loaf's I²C bus directly. G3 has no controller board.

The repository was named Loaf_ESPT until 2026-11-27. It is a controller, not a Loaf: the board has an ESP32 Thing Plus footprint and no Slice slot headers. It reached the bus through the 1x10 chain connector.

## Design

The board carries the bus connectors, an ESP32 Thing Plus, a 12 V to 5 V regulator, 3.3 V to 5 V logic level shifting (BSS138, with 10 kΩ pull-ups to +5 V on E_STOP, INT and SYNC), and I²C pull-ups to +3.3 V with an LTC4311 rise-time accelerator. Slice Interface 1 in bread-infra (`spec/slice/slice-interface-1.md`) describes how it meets the bus.

## Assessment

The ESP32 controller was built in place of a Raspberry Pi during the Pi shortage of those years, more than on a technical case, and it did not work well. rev.C fixed the board's hardware shortcomings, but the ESP32 itself was the bigger limit, so the work stopped there.

## Documentation

Please refer to the [docs](/docs) for more info.

---

<div align="center">
  <p>
    <img src="https://img.shields.io/badge/Developed_by-UWO--FAST--et--al-orange" alt="Developed by UWO-FAST et al.">
    <img src="https://img.shields.io/badge/Powered_by-Open_Source-blue" alt="Powered by Open Source">
  </p>
</div>
