# Validation test cases

## Historical Cases A–D

These four cases come from the historical TI-81 article and were used during SUNSIGHT development.

The numerical results below were rechecked against the current SUNSIGHT calculation code. The intercepts and Zn values remain unchanged. Case A also displays the low-Sun caution because its apparent altitude Ha is below 5°.

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

### Historical USNO comparison

| Case | SUNSIGHT GHA | USNO GHA | SUNSIGHT Dec | USNO Dec | SUNSIGHT Hc | USNO Hc | SUNSIGHT Zn | USNO Zn |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| A | 100°23.030′ | 100°23.1′ | N 7°12.035′ | N 7°12.0′ | 1°29.503′ | 1°29.4′ | 282.786° | 282.8° |
| B | 183°57.241′ | 183°57.4′ | N 23°26.035′ | N 23°26.0′ | 49°59.211′ | 49°59.3′ | 5.779° | 5.8° |
| C | 148°01.779′ | 148°01.8′ | S 0°34.354′ | S 0°34.4′ | 75°42.919′ | 75°43.0′ | 89.827° | 89.8° |
| D | 200°36.939′ | 200°37.1′ | S 21°13.895′ | S 21°13.9′ | 25°49.740′ | 25°49.7′ | 234.290° | 234.3° |

Maximum differences across A–D were about 0.16′ in GHA, 0.05′ in declination, 0.10′ in Hc and 0.03° in Zn.

## Modern USNO validation suite — 2026–2036

A second validation suite was run against the U.S. Naval Observatory *Celestial Navigation Data for Assumed Position and Time* page to exercise north/south latitudes, east/west longitudes, and low, medium, high and near-zenith Sun altitudes.

All ten modern cases use the same sight-correction conditions so that the comparison is clean:

- lower limb
- index error 0.0′
- height of eye 0.0 m
- pressure 1010 mb
- temperature 10 °C

With zero index error and zero height of eye, the entered Hs is also the apparent altitude Ha used by SUNSIGHT.

USNO values below are the displayed values transcribed from the USNO page. USNO displays GHA, declination, Hc and correction terms to 0.1′ and Zn to 0.1°, so differences smaller than roughly half of those displayed increments are not significant at the precision shown by the page.

### Test inputs and SUNSIGHT results

| Case | Date / UTC | Assumed position | Hs lower limb | SUNSIGHT result | Caution |
|---:|---|---|---:|---|---|
| 1 | 2026-02-15 15:46:17 | N 48°12.3′ W 123°45.6′ | 3°04.1′ | **3.0 To, Zn 112.7°** | **LOW SUN / USE WITH CAUTION** |
| 2 | 2027-06-21 02:32:42 | N 23°20.0′ E 140°15.0′ | 87°52.0′ | **2.0 From, Zn 86.4°** | **SUN NEAR ZENITH / USE WITH CAUTION** |
| 3 | 2028-10-05 13:02:05 | S 34°15.0′ E 18°30.0′ | 44°51.2′ | **4.0 To, Zn 302.1°** | None |
| 4 | 2029-12-21 16:05:33 | S 23°10.0′ W 70°20.0′ | 81°51.3′ | **3.0 From, Zn 93.6°** | None |
| 5 | 2030-12-01 12:44:51 | N 25°30.0′ E 55°15.0′ | 7°45.6′ | **2.0 To, Zn 241.2°** | None |
| 6 | 2031-07-10 23:02:09 | S 17°20.0′ W 149°30.0′ | 47°39.9′ | **4.0 From, Zn 339.5°** | None |
| 7 | 2032-09-22 11:30:27 | N 60°00.0′ E 5°30.0′ | 29°50.1′ | **5.0 To, Zn 180.0°** | None |
| 8 | 2033-01-15 05:29:44 | S 45°10.0′ W 170°15.0′ | 14°34.8′ | **5.0 From, Zn 254.9°** | None |
| 9 | 2034-05-20 03:07:12 | N 15°30.0′ E 120°45.0′ | 77°53.1′ | **3.0 To, Zn 66.2°** | None |
| 10 | 2036-11-05 12:34:36 | S 5°20.0′ W 35°40.0′ | 64°50.6′ | **2.0 From, Zn 117.0°** | None |

### Ephemeris and sight-reduction comparison

To keep the comparison readable on normal screens, each quantity is shown in its own compact table. Differences are absolute values.

#### Greenwich Hour Angle (GHA)

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | 53°03.3′ | 53°02.952′ | 0.348′ |
| 2 | 217°45.3′ | 217°45.049′ | 0.251′ |
| 3 | 18°27.7′ | 18°27.563′ | 0.137′ |
| 4 | 61°49.0′ | 61°48.975′ | 0.025′ |
| 5 | 13°57.2′ | 13°57.131′ | 0.069′ |
| 6 | 164°10.4′ | 164°10.214′ | 0.186′ |
| 7 | 354°29.2′ | 354°28.728′ | **0.472′** |
| 8 | 260°05.1′ | 260°04.950′ | 0.150′ |
| 9 | 227°39.7′ | 227°39.704′ | 0.004′ |
| 10 | 12°45.1′ | 12°44.905′ | 0.195′ |

#### Declination

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | S 12°31.4′ | S 12°31.252′ | 0.148′ |
| 2 | N 23°26.2′ | N 23°26.202′ | 0.002′ |
| 3 | S 5°03.7′ | S 5°03.803′ | 0.103′ |
| 4 | S 23°26.1′ | S 23°26.110′ | 0.010′ |
| 5 | S 21°51.0′ | S 21°51.018′ | 0.018′ |
| 6 | N 22°09.4′ | N 22°09.330′ | 0.070′ |
| 7 | S 0°00.3′ | S 0°00.504′ | **0.204′** |
| 8 | S 21°03.5′ | S 21°03.419′ | 0.081′ |
| 9 | N 19°58.4′ | N 19°58.449′ | 0.049′ |
| 10 | S 15°56.4′ | S 15°56.448′ | 0.048′ |

#### Calculated altitude (Hc)

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | 3°03.8′ | 3°03.299′ | **0.501′** |
| 2 | 88°09.9′ | 88°09.729′ | 0.171′ |
| 3 | 45°02.2′ | 45°02.354′ | 0.154′ |
| 4 | 82°10.4′ | 82°10.446′ | 0.046′ |
| 5 | 7°53.2′ | 7°53.255′ | 0.055′ |
| 6 | 47°58.8′ | 47°58.877′ | 0.077′ |
| 7 | 29°59.7′ | 29°59.495′ | 0.205′ |
| 8 | 14°52.4′ | 14°52.540′ | 0.140′ |
| 9 | 78°05.7′ | 78°05.716′ | 0.016′ |
| 10 | 65°08.5′ | 65°08.393′ | 0.107′ |

#### Azimuth (Zn)

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | 112.7° | 112.672° | 0.028° |
| 2 | 86.4° | 86.380° | 0.020° |
| 3 | 302.1° | 302.053° | 0.047° |
| 4 | 93.6° | 93.649° | **0.049°** |
| 5 | 241.2° | 241.160° | 0.040° |
| 6 | 339.5° | 339.488° | 0.012° |
| 7 | 180.0° | 179.976° | 0.024° |
| 8 | 254.9° | 254.924° | 0.024° |
| 9 | 66.2° | 66.235° | 0.035° |
| 10 | 117.0° | 117.042° | 0.042° |

Across the ten 2026–2036 cases, the largest absolute displayed-value differences were approximately:

- **GHA: 0.47′** — Case 7
- **declination: 0.20′** — Case 7
- **Hc: 0.50′** — Case 1
- **Zn: 0.05°** — Case 4

### Sight-correction comparison

The correction terms are also split into compact tables so each USNO value can be compared directly with SUNSIGHT.

#### Refraction

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | −14.2′ | −14.173′ | 0.027′ |
| 2 | −0.0′ | −0.022′ | 0.022′ |
| 3 | −1.0′ | −0.972′ | 0.028′ |
| 4 | −0.1′ | −0.126′ | 0.026′ |
| 5 | −6.8′ | −6.749′ | 0.051′ |
| 6 | −0.9′ | −0.880′ | 0.020′ |
| 7 | −1.7′ | −1.691′ | 0.009′ |
| 8 | −3.7′ | −3.686′ | 0.014′ |
| 9 | −0.2′ | −0.196′ | 0.004′ |
| 10 | −0.5′ | −0.447′ | 0.053′ |

#### Semidiameter (SD)

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | 16.2′ | 16.192′ | 0.008′ |
| 2 | 15.7′ | 15.739′ | 0.039′ |
| 3 | 16.0′ | 15.995′ | 0.005′ |
| 4 | 16.3′ | 16.258′ | 0.042′ |
| 5 | 16.2′ | 16.219′ | 0.019′ |
| 6 | 15.7′ | 15.732′ | 0.032′ |
| 7 | 15.9′ | 15.936′ | 0.036′ |
| 8 | 16.3′ | 16.260′ | 0.040′ |
| 9 | 15.8′ | 15.807′ | 0.007′ |
| 10 | 16.1′ | 16.132′ | 0.032′ |

#### Parallax in altitude (PA)

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | 0.1′ | 0.148′ | 0.048′ |
| 2 | 0.0′ | 0.005′ | 0.005′ |
| 3 | 0.1′ | 0.103′ | 0.003′ |
| 4 | 0.0′ | 0.020′ | 0.020′ |
| 5 | 0.1′ | 0.147′ | 0.047′ |
| 6 | 0.1′ | 0.097′ | 0.003′ |
| 7 | 0.1′ | 0.126′ | 0.026′ |
| 8 | 0.1′ | 0.144′ | 0.044′ |
| 9 | 0.0′ | 0.030′ | 0.030′ |
| 10 | 0.1′ | 0.062′ | 0.038′ |

#### Net sight correction (Sum)

| Case | USNO | SUNSIGHT | Difference |
|---:|---:|---:|---:|
| 1 | 2.1′ | 2.167′ | 0.067′ |
| 2 | 15.7′ | 15.722′ | 0.022′ |
| 3 | 15.1′ | 15.127′ | 0.027′ |
| 4 | 16.1′ | 16.153′ | 0.053′ |
| 5 | 9.5′ | 9.618′ | **0.118′** |
| 6 | 14.9′ | 14.949′ | 0.049′ |
| 7 | 14.3′ | 14.371′ | 0.071′ |
| 8 | 12.7′ | 12.718′ | 0.018′ |
| 9 | 15.6′ | 15.641′ | 0.041′ |
| 10 | 15.7′ | 15.748′ | 0.048′ |

The largest difference between SUNSIGHT's full-precision net sight correction and the USNO **displayed** Sum is about **0.12′**. Because the individual USNO correction terms and Sum are displayed only to 0.1′, part of this apparent difference is display rounding rather than necessarily a difference in the underlying USNO calculation.

The modern suite therefore shows good agreement over both hemispheres, east and west longitudes, and observed altitudes from about 3° to 88°. The low-altitude Case 1 is the largest Hc difference in this set; the correction calculation itself remains close to the USNO displayed correction.
