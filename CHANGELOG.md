# Changelog

## Unreleased — 2026-09-16

- Moved low-Sun and near-zenith cautions onto the main result screen so the result remains visible with the warning.
- Added a large-intercept caution at intercept magnitude > 25 NM with guidance to replot using a better DR/assumed position.
- Low-Sun caution remains based on apparent altitude Ha < 5°.
- Near-zenith caution is now based on corrected observed altitude Ho > 87°.
- Updated `SUNSIGHT.8xp`, `SUNSIGHT.txt`, and the line-by-line annotated source to the current tested build.
- Added a ten-case 2026–2036 validation suite against U.S. Naval Observatory celestial-navigation output using standard comparison conditions: lower limb, zero index error, zero height of eye, 1010 mb and 10 °C.
- The modern suite exercises north/south latitudes, east/west longitudes, and Sun altitudes from about 3° to 88°.
- Across the ten modern cases, the largest observed differences from the USNO displayed values were about 0.47′ in GHA, 0.20′ in declination, 0.50′ in Hc and 0.05° in Zn. The largest difference in displayed net sight correction was about 0.12′.

## v1.0.0 — 2026-09-12

Initial public-test version of SUNSIGHT for the **plain monochrome TI-84 Plus**.

- Tested on the plain TI-84 Plus.
- Calculator program size: 6,734 bytes.
- Supported date range: 1900–2049.
- Includes Meeus-based solar ephemeris, ΔT handling, marine sight corrections, pressure/temperature-adjusted refraction, input checking and low-altitude/near-zenith cautions.
- Installable file: `SUNSIGHT.8xp`.
- Validated against historical Cases A–D and U.S. Naval Observatory celestial-navigation data.
- Public documentation includes the human-readable source, line-by-line annotation, installation instructions, sources and validation tables.
- SUNSIGHT software code released under the MIT License, Copyright © 2026 Rob Murray.
- Articles and non-code documentation remain Copyright © 2026 Rob Murray, all rights reserved, except where third-party rights are identified.
