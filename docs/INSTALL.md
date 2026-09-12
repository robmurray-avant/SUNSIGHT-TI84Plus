# Installing SUNSIGHT on a plain TI-84 Plus

SUNSIGHT was written and tested on the **plain monochrome Texas Instruments TI-84 Plus**.

The preferred installation file is [`SUNSIGHT.8xp`](../SUNSIGHT.8xp). Do not use the annotated files for installation, and do not paste `SUNSIGHT.txt` into the calculator unless you specifically understand and intend to deal with TI-BASIC tokenization details.

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
Intercept  11.3 To
Zn         282.8
```

If your calculator does not produce that result, do not rely on the installation until the problem is understood.

Cases B–D are in [`test-cases.md`](test-cases.md).

## Supported range

The program accepts years **1900 through 2049**.

## Notes about the text source

`SUNSIGHT.txt` is provided so the tested TI-BASIC source can be inspected and documented. TI-BASIC pasted through an editor can be altered by tokenization, Unicode substitutions, whitespace handling and visually similar characters. The `.8xp` file avoids those problems and should be used for normal installation.

If you encounter a problem, open a GitHub issue and include the SUNSIGHT version, calculator model, all inputs, expected result if known, actual result, and whether Case A passes on the same calculator.
