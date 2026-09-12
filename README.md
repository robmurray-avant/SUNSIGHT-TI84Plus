# SUNSIGHT for the TI-84 Plus

SUNSIGHT is a Sun-sight reduction program for the **plain monochrome Texas Instruments TI-84 Plus**.

It is intended as a simple, independent celestial-navigation backup for offshore use. The program was written and tested on the TI-84 Plus and is deliberately limited to the Sun.

Enter the sight data and SUNSIGHT returns only the two values normally needed to plot the line of position:

```text
Intercept  11.3 To
Zn         282.8
```

The intercept is shown to 0.1 nautical mile and Zn to 0.1°. The program also gives caution messages for low-altitude sights and sights close to the zenith.

## What this project is

This repository contains the tested TI-BASIC program, documentation explaining how it works, historical material on the TI-81 program that inspired it, and test cases used to validate the new version.

SUNSIGHT is a modern rewrite of the idea behind William S. Murdock's 1996 TI-81 Sun-sight program. Murdock fitted a complete Sun ephemeris and sight-reduction system into **2,259 bytes**. The present TI-84 Plus version uses **6,734 bytes** and spends the extra capacity on a Meeus-based solar ephemeris, ΔT handling, refined refraction, input checking, clearer prompts and numerical safeguards.

The current program has been checked against the four historical examples provided and against multiple sets of U.S. Naval Observatory celestial-navigation data. Across all tested cases, the largest difference from in calculated altitude Hc was about 0.1 minute of arc, and the largest difference in Zn was about 0.03°.

## Download and install

Use [`SUNSIGHT.8xp`](SUNSIGHT.8xp) as the executable source.

It is formatted for transfer with **TI Connect CE**. Do not paste the annotated version or the *.txt version into the calculator. This will induce frustration, sadness and regret.

Before relying on the program, run the supplied test cases on the actual calculator you intend to carry aboard.

## Repository contents

- [`SUNSIGHT.8xp`](SUNSIGHT.8xp) the executable source for copying to the target TI-84 Plus calculator with the TI Connect CE software
- [`SUNSIGHT.txt`](SUNSIGHT.txt) — exact tested TI-BASIC source as a text file.
- [`SUNSIGHT_ANNOTATED.md`](SUNSIGHT_ANNOTATED.md) — index to a line-by-line explanation of the code.
- [`docs/annotated/`](docs/annotated/) — the full commented source, split into readable sections.
- [`docs/test-cases.md`](docs/test-cases.md) — Cases A–D and the USNO comparison.
- [`docs/sources.md`](docs/sources.md) — astronomical, refraction, historical and TI references.
- [`docs/original-cruising-world-1996/`](docs/original-cruising-world-1996/) — citation and links for Murdock's March 1996 *Cruising World* article, **“Create Your Own Sun-Sight Reduction Program.”** Copyrighted magazine scans are not redistributed here.
- [`docs/article-1-celestial-navigator.md`](docs/article-1-celestial-navigator.md) — draft article on the program, its development and intended use.

## Required inputs

SUNSIGHT asks for:

- date and UTC
- latitude and longitude
- sextant altitude Hs
- lower or upper limb
- index error, on or off the arc
- height of eye in metres
- atmospheric pressure in mb/hPa
- temperature in °C

North/South, East/West, limb and index-error direction are entered as numbered choices to reduce the chance of sign mistakes.

## Standard acceptance test — Case A

Enter:

- Date: **8 Apr 1950**
- UTC: **18:43:28**
- Position: **N 62°28.2′, E 000°18.8′**
- Hs: **1°38.2′**
- Limb: **lower**
- Index error: **10.2′ off the arc**
- Height of eye: **2.2 m**
- Pressure: **1050 mb/hPa**
- Temperature: **2 °C**

Expected result:

```text
Intercept  11.3 To
Zn         282.8
```

Cases B–D are in [`docs/test-cases.md`](docs/test-cases.md).

## Why Sun only?

For a cruiser whose celestial-navigation skills may be rusty, the Sun is a particularly useful backup body. It is easy to identify, normally gives a clear daytime horizon, and two sights separated by time can be used for a **Sun-run-Sun running fix** by advancing the first line of position by the vessel's course and distance before plotting the second.

The aim is not to replace a full celestial-navigation practice. It is to provide a compact, independent way of reducing Sun sights when normal electronic navigation is unavailable.

## Disclaimer:

This software is an educational and backup navigation tool, not a substitute for experience, education, judgment or common sense. While I have tested it extensively against the U.S. Naval Observatory’s “Celestial Navigation Data for Assumed Position and Time” and other authoritative sources, and it generally behaves itself and delivers accurate results, I cannot guarantee perfection (just ask Debra). A correct calculation will not save you from bad sights, a watch that has wandered off UTC, a rubbish DR, or classic “I typed 62° instead of 26°” type errors. Garbage in, garbage out remains undefeated. Test it yourself. Keep and use other independent means of finding out where you are. And remember: this program will not make you taller or better looking, alleviate hangover symptoms, or prevent you from hitting something solid if you ignore the results. Use at your own risk, preferably while (reasonably) sober. *****
