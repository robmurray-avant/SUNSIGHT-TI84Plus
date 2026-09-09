# SUNSIGHT for the TI-84 Plus

SUNSIGHT is a dedicated Sun-sight reduction program for the **plain monochrome Texas Instruments TI-84 Plus**.

It was written and tested on the TI-84 Plus as a simple, independent backup for offshore celestial navigation.
Enter date/UTC, position, sextant altitude, Sun limb, index error, height of eye, pressure and temperature.
The normal result is deliberately limited to:

- intercept, to one decimal nautical mile, **To** or **From**
- **Zn**, to one decimal degree

The program also warns when observed altitude is low or the Sun is near the zenith.

## Files

- `SUNSIGHT.txt` — exact tested TI Connect CE source.
- `SUNSIGHT_ANNOTATED.md` — the same program explained line by line; **documentation only**, not executable source.
- `docs/test-cases.md` — four historical test cases and the USNO comparison.
- `docs/original-cruising-world-1996/` — four images of William S. Murdoch's March 1996 *Cruising World* TI-81 article.

## Program size

The tested TI-84 Plus program occupies **6,734 bytes** on the calculator.
Murdoch's original TI-81 program occupied **2,259 bytes**.

## Standard test — Case A

- Date: 8 Apr 1950
- UTC: 18:43:28
- Position: N 62°28.2′, E 000°18.8′
- Hs: 1°38.2′
- Lower limb
- Index error: 10.2′ off arc
- Height of eye: 2.2 m
- Pressure: 1050 mb/hPa
- Temperature: 2 °C

Expected operational result:

```text
Intercept  11.3 To
Zn         282.8
```

## Important

This software is intended as an educational and backup navigation tool. Test the program and your calculator against the supplied cases before relying on it, and retain competent navigation practice and independent means of determining position.
