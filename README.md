# SUNSIGHT for the TI-84 Plus

SUNSIGHT is a Sun-sight reduction program for the **plain monochrome Texas Instruments TI-84 Plus**.

It is intended as a simple, independent celestial-navigation backup for offshore use. The program was written and tested on the plain TI-84 Plus and is deliberately limited to the Sun.

**Current public-test version: v1.0.0 — 2026-09-12**

Enter the sight data and SUNSIGHT returns the two values normally needed to plot a line of position:

```text
Intercept  11.3 To
Zn         282.8
```

The intercept is shown to 0.1 nautical mile and Zn to 0.1°. The program also gives caution messages for low-altitude sights and sights close to the zenith.

## What this project is

SUNSIGHT is a modern rewrite of the idea behind William S. **Murdoch's** 1996 TI-81 Sun-sight program. Murdoch fitted a complete Sun ephemeris and sight-reduction system into **2,259 bytes**. The present TI-84 Plus version occupies **6,734 bytes on the calculator** and spends the extra capacity on a Meeus-based solar ephemeris, ΔT handling, refined refraction, input checking, clearer prompts and numerical safeguards.

The current program has been checked against the four historical examples supplied with Murdoch's article and against U.S. Naval Observatory celestial-navigation data. Across Cases A–D, the largest difference in calculated altitude Hc was about **0.10 minute of arc**, and the largest difference in Zn was about **0.03°**.

Supported dates are **1900 through 2049**.

## Download and install

Use **[`SUNSIGHT.8xp`](SUNSIGHT.8xp)** to install the program on the calculator.

1. Install Texas Instruments **TI Connect CE** on your computer.
2. Connect the plain TI-84 Plus by USB.
3. Transfer `SUNSIGHT.8xp` to the calculator.
4. Run `SUNSIGHT` from the calculator's program menu.
5. Run **Case A** below before relying on the installation.

Do **not** paste `SUNSIGHT.txt` or any annotated file into the calculator. The `.txt` file is provided as a human-readable representation of the tested source; the annotated files are documentation only. TI-BASIC tokenization is fussy enough without inviting additional trouble.

## Repository contents

- [`SUNSIGHT.8xp`](SUNSIGHT.8xp) — installable TI-84 Plus program for transfer with TI Connect CE.
- [`SUNSIGHT.txt`](SUNSIGHT.txt) — human-readable text representation of the tested TI-BASIC source.
- [`SUNSIGHT_ANNOTATED.md`](SUNSIGHT_ANNOTATED.md) — index to the line-by-line explanation of the code.
- [`docs/annotated/`](docs/annotated/) — the full commented source, split into readable sections.
- [`docs/INSTALL.md`](docs/INSTALL.md) — installation and acceptance-test instructions.
- [`docs/test-cases.md`](docs/test-cases.md) — Cases A–D and the USNO comparison.
- [`docs/sources.md`](docs/sources.md) — astronomical, refraction, historical and TI references.
- [`docs/original-cruising-world-1996/`](docs/original-cruising-world-1996/) — citation and authorized online links for Murdoch's March 1996 *Cruising World* article. Copyrighted magazine scans are not redistributed here.
- [`docs/article-1-celestial-navigator.md`](docs/article-1-celestial-navigator.md) — draft article on the program, its development and intended use.
- [`CHANGELOG.md`](CHANGELOG.md) — public version history.

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

## Reporting a problem

Independent testing is welcome. Please open a GitHub issue and include:

- SUNSIGHT version
- exact calculator model
- all sight inputs
- expected result, if known
- actual result
- whether Case A passes on the same calculator
- any relevant error message or unusual behaviour

A bug-report template is provided automatically when opening an issue.

## Why Sun only?

For a cruiser whose celestial-navigation skills may be rusty, the Sun is a particularly useful backup body. It is easy to identify, normally gives a clear daytime horizon, and two sights separated by time can be used for a **Sun-run-Sun running fix** by advancing the first line of position by the vessel's course and distance before plotting the second.

The aim is not to replace a full celestial-navigation practice. It is to provide a compact, independent way of reducing Sun sights when normal electronic navigation is unavailable.

## Disclaimer

This software is an educational and backup navigation tool, not a substitute for experience, education, judgment or common sense. It has been tested extensively against the U.S. Naval Observatory's **Celestial Navigation Data for Assumed Position and Time** and other authoritative sources, but perfection is not guaranteed. A correct calculation cannot compensate for a bad sight, wrong UTC, a poor DR position or incorrectly entered data. Test the program independently and keep other means of determining position.
