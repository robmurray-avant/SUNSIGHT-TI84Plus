# Installing SUNSIGHT on a plain TI-84 Plus

SUNSIGHT v1.1.0 was written and tested on the **plain monochrome Texas Instruments TI-84 Plus**.

Version 1.1 installs under the program name `SUNSIGHT`, occupies **6,997 bytes on the calculator**, and the installable `.8xp` file is **7,056 bytes**. Use the `.8xp` file for installation; `SUNSIGHT.txt` and the annotated files are provided for reading and documentation.

The v1.1.0 `SUNSIGHT.8xp` SHA-256 is **`5754b6f24b85d4aca1a5b2dd7a45d2f8f69e62e311aef9b02977539707d0690f`**.

## Installation

1. Install **TI Connect CE** from Texas Instruments.
2. Connect the TI-84 Plus to the computer by USB.
3. Download `SUNSIGHT.8xp` from this repository.
4. Transfer `SUNSIGHT.8xp` to the calculator with TI Connect CE.
5. On the calculator, press `PRGM`, select `SUNSIGHT`, and run it.

## Acceptance test

Before relying on the program, enter Case A exactly:

- Date: 8 Apr 1950
- UTC: 18:43:28
- Position: N 62°28.2′, E 000°18.8′
- Hs: 1°38.2′
- Limb: lower
- Index error: 10.2′ off the arc
- Height of eye: 2.2 m
- Pressure: 1050 mb/hPa
- Temperature: 2 °C

Expected result:

```text
Sun sight
Int NM 11.4 To
Zn   282.8

LOW SUN
USE WITH CAUTION
```

The low-Sun caution is expected in Case A because the calculated apparent altitude Ha is about 1.76°, below the program's 5° caution threshold.

If your calculator does not produce that result, do not rely on the installation until the problem is understood.

Additional historical and modern validation cases are in [`test-cases.md`](test-cases.md).

## Supported range

The program accepts years **1900 through 2049**.

## Notes about the text source

`SUNSIGHT.txt` is a human-readable rendering of the v1.1 TI-BASIC program for inspection and documentation. For normal installation, use the released `SUNSIGHT.8xp` file.

If you encounter a problem, open a GitHub issue and include the SUNSIGHT version, calculator model, all inputs, expected result if known, actual result, and whether Case A passes on the same calculator.
