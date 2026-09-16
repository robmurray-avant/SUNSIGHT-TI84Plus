# Changelog

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
- Validated against the four historical Cases A–D and against U.S. Naval Observatory celestial-navigation data.
- Added a ten-case 2026–2036 USNO validation suite using standard comparison conditions: lower limb, zero index error, zero height of eye, 1010 mb and 10 °C.
- The modern suite exercises north/south latitudes, east/west longitudes, and Sun altitudes from about 3° to 88°.
- Across the ten modern cases, the largest observed differences from the USNO displayed values were about 0.47′ in GHA, 0.20′ in declination, 0.50′ in Hc and 0.05° in Zn. The largest difference in displayed net sight correction was about 0.12′.
- Public documentation includes the human-readable source, line-by-line annotation, installation instructions, memory map, sources and validation tables.
- SUNSIGHT software code is released under the MIT License, Copyright © 2026 Rob Murray.
- Articles and non-code documentation remain Copyright © 2026 Rob Murray, all rights reserved, except where third-party rights are identified.
