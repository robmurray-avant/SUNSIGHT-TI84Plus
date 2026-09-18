# SUNSIGHT for the TI-84 Plus

SUNSIGHT is a Sun-sight reduction program for the **plain monochrome Texas Instruments TI-84 Plus**.

It is intended as a simple, independent celestial-navigation backup for offshore use. The program was written and tested on the plain TI-84 Plus and is deliberately limited to the Sun.

**Release branch: v1.1.0 — 2026-09-18**

Enter the sight data and SUNSIGHT returns the two values normally needed to plot a line of position, with any applicable caution on the same screen:

```text
Sun sight
Int NM 11.3 To
Zn   282.8

LOW SUN
USE WITH CAUTION
```

The intercept is shown to 0.1 nautical mile and Zn to 0.1°. When applicable, the result screen also gives cautions for a low Sun, a Sun close to the zenith, or an intercept greater than 25 NM.

## What this project is

SUNSIGHT is a modern rewrite of the idea behind William S. **Murdoch's** 1996 TI-81 Sun-sight program. Murdoch fitted a complete Sun ephemeris and sight-reduction system into **2,259 bytes**. The original v1.0 TI-84 Plus release occupied **6,761 bytes on the calculator**. Version 1.1 retains the same compact Meeus-style solar model and adds eight small periodic longitude terms derived from VSOP87D to improve the ephemeris without adopting SUNSITE2's larger VSOP87D architecture.

SUNSIGHT is an independent modern implementation inspired by Murdoch's TI-81 work. **Murdoch's original program and article are not included in, or licensed under, the SUNSIGHT MIT License. Copyright in those materials remains with their respective rights holders.**

Version 1.1 was hardware-tested on a plain monochrome TI-84 Plus with historical Cases A–D; all four completed successfully. For ephemeris validation, the exact v1.1 formulas were also run off-calculator against a ten-case 2026–2036 USNO set and against the reconstructed Murdoch article code. Across those ten modern cases, v1.1's mean absolute GHA difference from the displayed USNO values was **0.044′**, with a maximum of **0.145′**; mean absolute declination difference was **0.032′**, with a maximum of **0.063′**. Murdoch's corresponding figures were **0.046′ / 0.103′** for GHA and **0.022′ / 0.048′** for declination. USNO displays these quantities to 0.1′, so differences of only a few hundredths of an arcminute should not be over-interpreted.

Supported dates are **1900 through 2049**.

## Accuracy in context: Murdoch, SUNSIGHT and the Nautical Almanac

It is useful to separate **ephemeris accuracy** from the accuracy of the final plotted line of position.

One minute of error in calculated altitude corresponds to approximately one nautical mile of intercept error. But once ephemeris error is below a few tenths of an arcminute, the dominant errors in a real marine sight are usually the sight itself: sextant reading, horizon definition, vessel motion, exact timing, index error, dip and atmospheric refraction.

| Method | Ephemeris / solar-position performance | Approximate ephemeris contribution to intercept error | Representative practical accuracy of a good small-boat Sun sight |
|---|---:|---:|---:|
| **Murdoch TI-81** | about **0.05′ mean GHA difference** in the 10-case modern USNO comparison; **0.103′ maximum** | roughly **0.1 NM class** in that comparison | roughly **1–2 NM** |
| **SUNSIGHT v1.1** | about **0.044′ mean GHA difference** in the same 10 cases; **0.145′ maximum**; broad 1900–2049 numerical testing gives about **0.059′ RMS GHA** | roughly **0.1–0.2 NM class** | roughly **1–2 NM** |
| **Standard Nautical Almanac method** | hourly Sun GHA and declination tabulated to **0.1′**; **Increments and Corrections** carry GHA to the sight minute/second and **d** interpolates declination | generally about **0.1 NM or less** from the tabular calculation | roughly **1–2 NM** |

The comparison is deliberately approximate. It is intended to show scale, not to imply that every sight will fall inside those bands or that **1–2 NM** is a guaranteed error envelope. A very good observer in settled conditions may do better; rough seas, a poor horizon or low altitude can make the result substantially worse.

**Why the two accuracy columns are so different:** the final LOP contains more than ephemeris error. It also contains observational error from the sextant reading, horizon definition, vessel motion, timing, dip, index error and atmospheric refraction. Once the ephemeris is accurate to a few tenths of an arcminute, those other errors usually dominate.

The standard *Nautical Almanac* remains the authoritative navigational reference. Its hourly Sun GHA and declination are published to **0.1′**. For a sight between whole hours, the navigator uses the **Increments and Corrections** tables to carry GHA to the exact minute and second of UTC and applies the **d correction** to interpolate declination.

**The practical lesson:** Murdoch's program was already capable of useful marine celestial navigation. SUNSIGHT v1.1 brings its compact Meeus-style ephemeris into roughly the same practical accuracy class as Murdoch's remarkably efficient 1996 implementation, while retaining SUNSIGHT's modern input handling, corrections and safeguards. The final real-world LOP still does not improve by the same amount because observational and atmospheric errors dominate.

That is the practical reason v1.1 stops at a small eight-term longitude correction rather than replacing SUNSIGHT's simple architecture with a much larger planetary theory.

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
- [`docs/test-cases.md`](docs/test-cases.md) — historical Cases A–D plus the ten-case 2026–2036 USNO validation suite.
- [`docs/memory-map.md`](docs/memory-map.md) — A–Z and `L₁` memory map, user-entered values, diagnostic values, and instructions for inspecting stored data.
- [`docs/sources.md`](docs/sources.md) — astronomical, refraction, historical and TI references.
- [`docs/original-cruising-world-1996/`](docs/original-cruising-world-1996/) — citation and authorized online links for Murdoch's March 1996 *Cruising World* article. Copyrighted magazine scans are not redistributed here.
- [`docs/article-1-celestial-navigator.md`](docs/article-1-celestial-navigator.md) — draft article on the program, its development and intended use.
- [`CHANGELOG.md`](CHANGELOG.md) — public version history.
- [`LICENSE`](LICENSE) — MIT License for the SUNSIGHT software code.
- [`COPYRIGHT.md`](COPYRIGHT.md) — copyright and licensing scope for the repository.

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

## Warnings and why they are there

SUNSIGHT gives three practical navigation cautions on the result screen.

### LOW SUN — apparent altitude below 5°

Refraction becomes rapidly larger and less predictable as altitude falls. SUNSIGHT calculates a standard correction from the entered pressure and temperature, but the real atmosphere may not behave like the model.

*The American Practical Navigator* (Bowditch) puts the problem plainly:

> “The atmosphere contains many irregularities which are erratic in their influence upon refraction.”

Bowditch notes that temperature inversions, fronts, squalls, differences between sea and air temperature and layered air can all produce abnormal refraction. Near the horizon, even a mathematically excellent ephemeris cannot remove that uncertainty.

National Geospatial-Intelligence Agency, *The American Practical Navigator (Bowditch)*, Pub. No. 9, 2024 edition, Vol. II, §605, “Astronomical Refraction,” p. 250. Official publication page: [https://msi.nga.mil/Publications/APN](https://msi.nga.mil/Publications/APN)

The LOW SUN warning therefore means exactly what it says: the result may still be useful, but it deserves less confidence than a sight taken at a healthier (higher) altitude.

### SUN NEAR ZENITH — corrected altitude above 87°

The near-zenith warning is mainly a geometry and plotting caution, not a refraction warning. As the Sun approaches the zenith, azimuth can change very rapidly and the circle of equal altitude becomes too tightly curved to be represented well by an ordinary straight line of position.

Bowditch states:

> “It is not always easy to determine the azimuth accurately, and when near the zenith, a body may be changing azimuth rapidly.”

It also warns that for a body near the zenith:

> “the use of a straight line to approximate the circle may introduce serious error.”

SUNSIGHT's 87° threshold corresponds closely to Bowditch's further guidance that within about three degrees of the zenith the circle of position should be plotted as a circle rather than treated as a straight LOP.

National Geospatial-Intelligence Agency, *The American Practical Navigator (Bowditch)*, Pub. No. 9, 2024 edition, Vol. I, §2011, “High Altitude Sights,” pp. 362–364. Official publication page: [https://msi.nga.mil/Publications/APN](https://msi.nga.mil/Publications/APN)

### INT >25 NM — large intercept

A large intercept does not necessarily mean the celestial calculation is wrong. It usually means the assumed or DR position is a poor centre from which to plot the line of position, or that an input deserves checking.

SUNSIGHT therefore advises:

`REPLOT BETTER DR`

The purpose is practical: use a more suitable assumed position and check the sight data rather than blindly plotting a very large intercept.

These are **navigation cautions, not calculation-error messages**.

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

Expected v1.1 result:

```text
Sun sight
Int NM 11.4 To
Zn   282.8

LOW SUN
USE WITH CAUTION
```

The low-Sun caution is expected in Case A because Ha is about 1.76°, below the 5° caution threshold.

Additional historical and modern validation cases are in [`docs/test-cases.md`](docs/test-cases.md).

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

## Copyright and license

The **SUNSIGHT software code** is Copyright © 2026 Rob Murray and is licensed under the **MIT License**. This includes `SUNSIGHT.8xp`, `SUNSIGHT.txt`, and reproductions or excerpts of the SUNSIGHT code in the annotated-source documentation. See [`LICENSE`](LICENSE).

The MIT License applies only to Rob Murray's original SUNSIGHT code. **It does not apply to William S. Murdoch's original TI-81 program, Murdoch's article, or any other third-party material.** Those materials remain subject to the rights of their respective copyright holders.

The **articles, explanatory documentation, historical notes and other non-code material** in this repository are Copyright © 2026 Rob Murray, **all rights reserved**, unless otherwise stated. Code excerpts embedded in documentation remain covered by the MIT License; the surrounding prose does not. See [`COPYRIGHT.md`](COPYRIGHT.md) for the full scope statement.

Third-party material remains subject to the rights of its respective owners.

## Disclaimer

This software is an educational and backup navigation tool, not a substitute for experience, education, judgment or common sense. While I have tested it extensively against the U.S. Naval Observatory’s “Celestial Navigation Data for Assumed Position and Time” and other authoritative sources, and it generally behaves itself and delivers accurate results, I cannot guarantee perfection (just ask Debra). A correct calculation will not save you from bad sights, a watch that has wandered off UTC, a rubbish DR, or classic “I typed 52° instead of 25°”-type errors. Garbage in, garbage out remains undefeated. Test it yourself. Keep and use other independent means of finding out where you are. And remember: this program will not make you taller or better looking, alleviate hangover symptoms, or prevent you from hitting something solid if you ignore the results. Use at your own risk, preferably while (reasonably) sober.
