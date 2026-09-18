# Validation test cases

## Historical Cases A–D — hardware regression

These four cases come from William S. Murdoch's 1996 TI-81 article and are the primary full-program hardware regression tests.

SUNSIGHT v1.1 was run on a **plain monochrome TI-84 Plus** with all four cases. All four completed successfully.

| Case | Date / UTC | Position | Hs / limb | IE | Eye | P / T | SUNSIGHT v1.1 result | Caution |
|---|---|---|---|---|---:|---|---|---|
| A | 1950-04-08 18:43:28 | N 62°28.2′ E 000°18.8′ | 1°38.2′ lower | 10.2′ off | 2.2 m | 1050 mb / 2°C | **11.4 To, Zn 282.8°** | **LOW SUN / USE WITH CAUTION** |
| B | 1972-06-23 00:17:52 | S 16°23.0′ E 172°00.0′ | 50°01.2′ lower | 10.2′ off | 3.4 m | 1010 mb / 10°C | **24.0 To, Zn 5.8°** | None |
| C | 1992-03-18 22:00:00 | S 00°38.1′ W 162°18.9′ | 76°24.8′ upper | 8.2′ on | 6.2 m | 970 mb / 40°C | **13.1 To, Zn 89.8°** | None |
| D | 1994-11-28 01:10:14 | N 18°17.2′ W 148°58.8′ | 25°40.7′ lower | 2.5′ on | 4.35 m | 1030 mb / 34°C | **0.7 From, Zn 234.3°** | None |

The exact v1.1 calculation gives:

| Case | GHA | Declination | Hc | Zn | Intercept |
|---|---:|---:|---:|---:|---:|
| A | 100°23.079′ | N 7°12.015′ | 1°29.463′ | 282.787° | +11.354 NM |
| B | 183°57.229′ | N 23°26.035′ | 49°59.210′ | 5.779° | +23.967 NM |
| C | 148°01.781′ | S 0°34.354′ | 75°42.921′ | 89.827° | +13.070 NM |
| D | 200°37.128′ | S 21°13.864′ | 25°49.612′ | 234.292° | −0.656 NM |

Positive intercept means **To**; negative means **From**.

### Historical USNO comparison

USNO displays GHA, declination and Hc to 0.1′ and Zn to 0.1°, so hundredths of an arcminute should not be treated as significant.

| Case | v1.1 GHA | USNO GHA | v1.1 Dec | USNO Dec | v1.1 Hc | USNO Hc | v1.1 Zn | USNO Zn |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| A | 100°23.079′ | 100°23.1′ | N 7°12.015′ | N 7°12.0′ | 1°29.463′ | 1°29.4′ | 282.787° | 282.8° |
| B | 183°57.229′ | 183°57.4′ | N 23°26.035′ | N 23°26.0′ | 49°59.210′ | 49°59.3′ | 5.779° | 5.8° |
| C | 148°01.781′ | 148°01.8′ | S 0°34.354′ | S 0°34.4′ | 75°42.921′ | 75°43.0′ | 89.827° | 89.8° |
| D | 200°37.128′ | 200°37.1′ | S 21°13.864′ | S 21°13.9′ | 25°49.612′ | 25°49.7′ | 234.292° | 234.3° |

Maximum absolute displayed-value differences across A–D are about **0.17′ GHA**, **0.05′ declination**, **0.09′ Hc**, and **0.03° Zn**.

## Modern ephemeris suite — 2026–2036

Cases 1–10 are used here as **ephemeris comparisons**. They do not need to be run through the normal calculator sight-entry UI. The exact SUNSIGHT v1.1 ephemeris formulas are evaluated off-calculator, and Murdoch's values are produced by running the reconstructed code from his published article.

The comparison is restricted to **GHA and declination** so differences in refraction and other sight-correction models do not contaminate the ephemeris comparison.

USNO displays GHA and declination to 0.1′. Accordingly, differences around or below 0.05′ are at or below the resolution of the displayed reference.

| Case | Date / time | USNO GHA | v1.1 GHA | v1.1 diff | Murdoch diff | USNO Dec | v1.1 Dec | v1.1 diff | Murdoch diff |
|---:|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 2026-02-15 15:46:17 | 53°03.3′ | 53°03.290′ | 0.010′ | 0.020′ | S 12°31.4′ | S 12°31.372′ | 0.028′ | 0.029′ |
| 2 | 2027-06-21 02:32:42 | 217°45.3′ | 217°45.298′ | 0.002′ | 0.006′ | N 23°26.2′ | N 23°26.201′ | 0.001′ | 0.009′ |
| 3 | 2028-10-05 13:02:05 | 18°27.7′ | 18°27.670′ | 0.030′ | 0.062′ | S 5°03.7′ | S 5°03.759′ | 0.059′ | 0.024′ |
| 4 | 2029-12-21 16:05:33 | 61°49.0′ | 61°48.965′ | 0.035′ | 0.028′ | S 23°26.1′ | S 23°26.110′ | 0.010′ | 0.000′ |
| 5 | 2030-12-01 12:44:51 | 13°57.2′ | 13°57.244′ | 0.044′ | 0.103′ | S 21°51.0′ | S 21°51.002′ | 0.002′ | 0.015′ |
| 6 | 2031-07-10 23:02:09 | 164°10.4′ | 164°10.413′ | 0.013′ | 0.043′ | N 22°09.4′ | N 22°09.355′ | 0.045′ | 0.048′ |
| 7 | 2032-09-22 11:30:27 | 354°29.2′ | 354°29.055′ | 0.145′ | 0.034′ | S 0°00.3′ | S 0°00.363′ | 0.063′ | 0.015′ |
| 8 | 2033-01-15 05:29:44 | 260°05.1′ | 260°05.092′ | 0.008′ | 0.102′ | S 21°03.5′ | S 21°03.444′ | 0.056′ | 0.042′ |
| 9 | 2034-05-20 03:07:12 | 227°39.7′ | 227°39.755′ | 0.055′ | 0.062′ | N 19°58.4′ | N 19°58.438′ | 0.038′ | 0.034′ |
| 10 | 2036-11-05 12:34:36 | 12°45.1′ | 12°45.005′ | 0.095′ | 0.001′ | S 15°56.4′ | S 15°56.417′ | 0.017′ | 0.009′ |

### Ten-case summary

| Ephemeris | Mean absolute GHA difference | Maximum GHA difference | Mean absolute Dec difference | Maximum Dec difference |
|---|---:|---:|---:|---:|
| **Murdoch article code** | **0.046′** | **0.103′** | **0.022′** | **0.048′** |
| **SUNSIGHT v1.1** | **0.044′** | **0.145′** | **0.032′** | **0.063′** |

The two compact methods are effectively in the same accuracy class at the resolution of the displayed USNO data. The table should not be used to claim that a few hundredths of an arcminute establishes superiority.

## Broad 1900–2049 numerical stress test

To look beyond the small USNO set, the exact v1.0 and v1.1 algorithms were compared with **Swiss Ephemeris apparent geocentric solar coordinates** every two days at 12:00 from 1900 through 2049: **27,394 epochs**.

Swiss Ephemeris is used here as a high-precision numerical reference, **not as USNO**.

| Version | GHA RMS | Maximum GHA | Declination RMS | Maximum declination |
|---|---:|---:|---:|---:|
| SUNSIGHT v1.0 | 0.201′ | 0.618′ | 0.059′ | 0.227′ |
| **SUNSIGHT v1.1** | **0.059′** | **0.196′** | **0.019′** | **0.073′** |

The eight-term correction therefore reduces GHA RMS error by about **71%** and maximum GHA error by about **68%** in this broad test.

## Warning thresholds

The navigation cautions are unchanged in v1.1:

- low Sun: apparent altitude Ha < 5°
- Sun near zenith: corrected observed altitude Ho > 87°
- large intercept: intercept magnitude > 25 NM
