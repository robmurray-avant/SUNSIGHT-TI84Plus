# Changelog

## v1.1.0 — 2026-09-18

Ephemeris accuracy update for the **plain monochrome TI-84 Plus**.

- Calculator program size: **6,997 bytes**; `.8xp` file size: **7,056 bytes**.
- Retains SUNSIGHT's compact Meeus-style solar model and overall sight-reduction architecture.
- Adds eight small periodic corrections to true solar longitude, derived from VSOP87D Earth longitude terms, stored in the new dedicated location `L₁(72)`.
- Expands `L₁` from 71 to 72 elements; no existing list element is repurposed.
- Hardware-tested on a plain monochrome TI-84 Plus with historical Cases A–D; all four passed.
- Updated expected historical results: Case A **11.4 To, Zn 282.8°**; B **24.0 To, Zn 5.8°**; C **13.1 To, Zn 89.8°**; D **0.7 From, Zn 234.3°**.
- In the ten-case 2026–2036 ephemeris comparison, v1.1 mean absolute GHA difference from the displayed USNO values is **0.044′**, maximum **0.145′**; mean absolute declination difference is **0.032′**, maximum **0.063′**.
- The reconstructed Murdoch article code gives **0.046′ mean / 0.103′ max GHA** and **0.022′ mean / 0.048′ max declination** over the same ten cases. Because USNO displays to 0.1′, differences of only a few hundredths of an arcminute should not be treated as significant.
- Broad off-calculator testing every two days from 1900 through 2049 (27,394 epochs) against Swiss Ephemeris apparent solar coordinates reduced GHA RMS error from about **0.201′** in v1.0 to **0.059′** in v1.1, with maximum GHA error reduced from about **0.618′** to **0.196′**. Swiss Ephemeris is used here as a high-precision numerical reference, not as USNO.
- Supported date range remains 1900–2049.
- User interface, marine sight corrections, warnings and output format are unchanged.

## v1.0.0 — 2026-09-16

First public release of SUNSIGHT for the **plain monochrome TI-84 Plus**.

- Tested on the plain TI-84 Plus.
- Calculator program size: **6,761 bytes**.
- Installable file: `SUNSIGHT.8xp`, internally named `SUNSIGHT`.
- Supported date range: 1900–2049.
- Includes a Meeus-based solar ephemeris, ΔT handling, marine sight corrections, pressure/temperature-adjusted refraction, input checking and numerical safeguards.
- Low-Sun caution is displayed on the result screen when apparent altitude Ha < 5°.
- Near-zenith caution is displayed when corrected observed altitude Ho > 87°.
- Large-intercept caution is displayed when intercept magnitude > 25 NM, with guidance to replot using a better DR/assumed position.
- Validated against historical Cases A–D and U.S. Naval Observatory celestial-navigation data.
- Public documentation includes the human-readable source, line-by-line annotation, installation instructions, memory map, sources and validation tables.
- SUNSIGHT software code is released under the MIT License, Copyright © 2026 Rob Murray.
