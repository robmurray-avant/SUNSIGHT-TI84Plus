# SUNSIGHT v1.1.0 release notes

**Date:** 2026-09-18  
**Target:** plain monochrome TI-84 Plus

## What changed

SUNSIGHT v1.1 keeps the compact Meeus-style solar ephemeris and adds eight small VSOP87D-derived periodic longitude terms. The goal is to improve solar GHA/declination materially without replacing SUNSIGHT with SUNSITE2's larger truncated-VSOP87D architecture.

The new correction is stored only in `L₁(72)`; existing list meanings are unchanged.

**Program size:** 6,997 bytes on calculator; 7,056-byte `.8xp` file.

## Validation

- Historical Cases A–D were run successfully on a physical plain TI-84 Plus.
- Expected v1.1 displayed results:
  - A: **11.4 To, Zn 282.8°**
  - B: **24.0 To, Zn 5.8°**
  - C: **13.1 To, Zn 89.8°**
  - D: **0.7 From, Zn 234.3°**
- Ten-case 2026–2036 ephemeris comparison against displayed USNO values:
  - v1.1 GHA mean absolute difference **0.044′**, maximum **0.145′**
  - v1.1 declination mean absolute difference **0.032′**, maximum **0.063′**
  - reconstructed Murdoch code over the same cases: GHA **0.046′ mean / 0.103′ max**; declination **0.022′ mean / 0.048′ max**
- Broad 1900–2049 stress test, 27,394 epochs against Swiss Ephemeris:
  - GHA RMS **0.059′**, max **0.196′**
  - declination RMS **0.019′**, max **0.073′**

USNO displays GHA/declination to 0.1′, so differences of only a few hundredths of an arcminute are at or below the resolution of the displayed reference.

## Tokenization

The tested text source uses:

- `sin(` and `tan(` for inverse trig
- literal `L₁`
- literal `√`
- a trailing space after every `Pause `

Do not normalize or substitute these characters when creating the TI-BASIC program.

## Release binary

The supplied v1.1 `SUNSIGHT.8xp` was built from the tested v1.1 source. It occupies **6,997 bytes on the calculator** and **7,056 bytes as a file**. The uploaded filename suffix `(4)` is not part of the release name; the repository file is `SUNSIGHT.8xp`.
