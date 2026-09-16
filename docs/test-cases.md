# Validation test cases

These four cases come from the historical TI-81 article and were used during SUNSIGHT development.

The numerical results below were rechecked against the current SUNSIGHT calculation code. The intercepts and Zn values remain unchanged. Case A now also displays the low-Sun caution because its apparent altitude Ha is below 5°.

| Case | Date / UTC | Position | Hs / limb | IE | Eye | P / T | SUNSIGHT result | Caution |
|---|---|---|---|---|---:|---|---|---|
| A | 1950-04-08 18:43:28 | N 62°28.2′ E 000°18.8′ | 1°38.2′ lower | 10.2′ off | 2.2 m | 1050 mb / 2°C | **11.3 To, Zn 282.8°** | **LOW SUN / USE WITH CAUTION** |
| B | 1972-06-23 00:17:52 | S 16°23.0′ E 172°00.0′ | 50°01.2′ lower | 10.2′ off | 3.4 m | 1010 mb / 10°C | **24.0 To, Zn 5.8°** | None |
| C | 1992-03-18 22:00:00 | S 00°38.1′ W 162°18.9′ | 76°24.8′ upper | 8.2′ on | 6.2 m | 970 mb / 40°C | **13.1 To, Zn 89.8°** | None |
| D | 1994-11-28 01:10:14 | N 18°17.2′ W 148°58.8′ | 25°40.7′ lower | 2.5′ on | 4.35 m | 1030 mb / 34°C | **0.8 From, Zn 234.3°** | None |

For reference, the current code gives these internal values at the warning tests:

| Case | Ha | Ho | Intercept magnitude | Warning trigger |
|---|---:|---:|---:|---|
| A | 1.763° | 1.680° | 11.314 NM | Ha < 5° |
| B | 50.136° | 50.386° | 23.966 NM | none |
| C | 76.204° | 75.933° | 13.072 NM | none |
| D | 25.575° | 25.816° | 0.784 NM | none |

The current caution thresholds are:

- low Sun: Ha < 5°
- Sun near zenith: Ho > 87°
- large intercept: intercept magnitude > 25 NM

## USNO comparison

| Case | SUNSIGHT GHA | USNO GHA | SUNSIGHT Dec | USNO Dec | SUNSIGHT Hc | USNO Hc | SUNSIGHT Zn | USNO Zn |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| A | 100°23.030′ | 100°23.1′ | N 7°12.035′ | N 7°12.0′ | 1°29.503′ | 1°29.4′ | 282.786° | 282.8° |
| B | 183°57.241′ | 183°57.4′ | N 23°26.035′ | N 23°26.0′ | 49°59.211′ | 49°59.3′ | 5.779° | 5.8° |
| C | 148°01.779′ | 148°01.8′ | S 0°34.354′ | S 0°34.4′ | 75°42.919′ | 75°43.0′ | 89.827° | 89.8° |
| D | 200°36.939′ | 200°37.1′ | S 21°13.895′ | S 21°13.9′ | 25°49.740′ | 25°49.7′ | 234.290° | 234.3° |

Maximum differences across A–D were about 0.16′ in GHA, 0.05′ in declination, 0.10′ in Hc and 0.03° in Zn.
