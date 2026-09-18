# SUNSIGHT memory map and diagnostic values

SUNSIGHT stores the user-entered sight data in the calculator's letter variables and the calculation intermediates in list `L₁`.

The program dimensions `L₁` to 72 elements. After a completed sight, the values remain available until another calculation overwrites them or the user changes them.

## How to inspect stored values

After SUNSIGHT has completed a sight, return to the calculator home screen. If necessary, press `ON` to interrupt the running program; the TI-84 Plus will show `ERR:BREAK`, from which you can choose **Quit**. This is a calculator error-menu choice, not a SUNSIGHT menu item.

- To inspect a letter variable, enter the letter and press `ENTER`. For example, entering `G` displays the stored signed latitude.
- To inspect a list element, enter `L₁(n)` and press `ENTER`. On the plain TI-84 Plus, `2nd` → `1` inserts `L₁`. For example, `L₁(39)` displays the calculated Sun GHA and `L₁(49)` displays Zn.
- To browse the list, press `STAT` → `1:Edit` and inspect the `L₁` column.
- Restarting SUNSIGHT does not deliberately erase A–O or `L₁`; the next completed sight overwrites the calculation locations.

The input variables A–O are persistent sight data. P and Q are temporary interface/scratch variables. R–Z are unused by the current program and therefore should not be assumed to contain zero.

## Most useful diagnostic values

This table combines the user-entered sight data with the principal calculated values useful for checking a sight against another source such as the U.S. Naval Observatory.

| Value | Memory location | Units / coding | Meaning |
|---|---|---|---|
| Year | `A` | year | User-entered UTC year |
| Month | `B` | 1–12 | User-entered UTC month |
| Day | `C` | 1–31 | User-entered UTC day |
| UTC hour | `D` | 0–23 | User-entered UTC hour |
| UTC minute | `E` | 0–59 | User-entered UTC minute |
| UTC second | `F` | seconds | User-entered UTC seconds |
| Latitude | `G` | decimal degrees | Assumed/DR latitude; North +, South − |
| Longitude | `H` | decimal degrees | Assumed/DR longitude; East +, West − |
| Hs degrees | `I` | degrees | Sextant altitude degree component |
| Hs minutes | `J` | arcminutes | Sextant altitude minute component |
| Limb | `K` | code | `1` = lower limb; `2` = upper limb |
| Index correction | `L` | arcminutes | Signed: off arc +, on arc − |
| Height of eye | `M` | metres | User-entered height of eye |
| Pressure | `N` | mb / hPa | User-entered atmospheric pressure |
| Temperature | `O` | °C | User-entered temperature |
| GHA | `L₁(39)` | degrees | Sun Greenwich Hour Angle, normalized 0–360° |
| Declination | `L₁(30)` | degrees | Sun declination; North +, South − |
| Hc | `L₁(43)` | degrees | Calculated altitude of the Sun centre |
| Zn | `L₁(49)` | degrees | Final azimuth, normalized 0–360° |
| Hs | `L₁(50)` | degrees | Sextant altitude converted to decimal degrees |
| Index correction | `L₁(51)` | degrees | Signed index correction used in the sight reduction |
| Dip | `L₁(52)` | degrees | Dip correction magnitude |
| Ha | `L₁(53)` | degrees | Apparent limb altitude after index correction and dip |
| Refraction | `L₁(58)` | arcminutes | Pressure/temperature-corrected refraction |
| Semidiameter | `L₁(61)` | degrees | Solar semidiameter magnitude |
| Signed semidiameter | `L₁(62)` | degrees | Positive for lower limb, negative for upper limb |
| Parallax in altitude | `L₁(64)` | degrees | Solar parallax in altitude |
| Ho | `L₁(65)` | degrees | Fully corrected observed altitude of the Sun centre |
| Signed intercept | `L₁(66)` | nautical miles | Positive = To; negative = From |
| Intercept magnitude | `L₁(67)` | nautical miles | Absolute intercept displayed by SUNSIGHT |

## Letter variables A–Z

| Location | Contents after a sight | Units / coding | Notes |
|---|---|---|---|
| `A` | Year | integer year | User input; valid 1900–2049 |
| `B` | Month | 1–12 | User input |
| `C` | Day | 1–31 | User input |
| `D` | UTC hour | 0–23 | User input |
| `E` | UTC minute | 0–59 | User input |
| `F` | UTC second | seconds | User input |
| `G` | DR / assumed latitude | decimal degrees | North +, South − |
| `H` | DR / assumed longitude | decimal degrees | East +, West − |
| `I` | Hs degree component | degrees | Sextant altitude degrees |
| `J` | Hs minute component | arcminutes | Sextant altitude minutes |
| `K` | Sun limb | code | `1` = lower limb; `2` = upper limb |
| `L` | Signed index correction | arcminutes | Off arc +, on arc − |
| `M` | Height of eye | metres | User input |
| `N` | Atmospheric pressure | mb / hPa | User input |
| `O` | Temperature | °C | User input |
| `P` | Temporary menu/scratch variable | varies | Not navigation data; do not rely on its stored value |
| `Q` | Temporary position-display scratch variable | varies | Used while converting decimal position back to degrees/minutes |
| `R` | Unused | — | SUNSIGHT does not initialize or modify it |
| `S` | Unused | — | SUNSIGHT does not initialize or modify it |
| `T` | Unused | — | SUNSIGHT does not initialize or modify it |
| `U` | Unused | — | SUNSIGHT does not initialize or modify it |
| `V` | Unused | — | SUNSIGHT does not initialize or modify it |
| `W` | Unused | — | SUNSIGHT does not initialize or modify it |
| `X` | Unused | — | SUNSIGHT does not initialize or modify it |
| `Y` | Unused | — | SUNSIGHT does not initialize or modify it |
| `Z` | Unused | — | SUNSIGHT does not initialize or modify it |

## List `L₁` calculation memory

| Location | Contents after a completed sight | Units | Description |
|---|---|---|---|
| `L₁(1)` | Adjusted year for Julian Date | year | Original year, or year − 1 for January/February |
| `L₁(2)` | Adjusted month for Julian Date | month | Original month, or month + 12 for January/February |
| `L₁(3)` | Gregorian century term | integer | `int(adjusted year / 100)` |
| `L₁(4)` | Gregorian calendar correction | days | `2 − century + int(century/4)` |
| `L₁(5)` | Julian Date, UTC | JD | Julian Date including UTC fraction of day |
| `L₁(6)` | Decimal year | year | Used to select/evaluate the ΔT polynomial |
| `L₁(7)` | ΔT polynomial time argument | years | Year offset from the base epoch for the applicable ΔT polynomial |
| `L₁(8)` | ΔT | seconds | TT − UT approximation |
| `L₁(9)` | Julian Date, TT | JD | UTC Julian Date corrected by ΔT |
| `L₁(10)` | Julian centuries TT from J2000.0 | centuries | Time argument for most solar ephemeris calculations |
| `L₁(11)` | Julian centuries UT from J2000.0 | centuries | Time argument used for sidereal time |
| `L₁(12)` | Geometric mean solar longitude, unnormalized | degrees | Meeus solar-longitude intermediate |
| `L₁(13)` | Geometric mean solar longitude | degrees | Normalized to 0–360° |
| `L₁(14)` | Solar mean anomaly, unnormalized | degrees | Meeus anomaly intermediate |
| `L₁(15)` | Solar mean anomaly | degrees | Normalized to 0–360° |
| `L₁(16)` | Earth's orbital eccentricity | dimensionless | Orbital eccentricity at the sight epoch |
| `L₁(17)` | Sun equation of centre | degrees | Correction from mean anomaly to true longitude |
| `L₁(18)` | True solar longitude, unnormalized | degrees | Mean longitude + equation of centre |
| `L₁(19)` | True solar longitude | degrees | Normalized to 0–360° |
| `L₁(20)` | Ω node-angle term | degrees | Approximate lunar-node angle used in apparent longitude/nutation corrections |
| `L₁(21)` | Apparent solar longitude, unnormalized | degrees | True longitude with apparent-position correction |
| `L₁(22)` | Apparent solar longitude | degrees | Normalized to 0–360° |
| `L₁(23)` | Mean obliquity of the ecliptic | degrees | Mean axial tilt |
| `L₁(24)` | Corrected obliquity | degrees | Obliquity including the Ω correction |
| `L₁(25)` | RA atan numerator | dimensionless | `cos(obliquity) × sin(apparent longitude)` |
| `L₁(26)` | RA atan denominator | dimensionless | `cos(apparent longitude)` |
| `L₁(27)` | Preliminary right ascension | degrees | Arctangent result before quadrant correction |
| `L₁(28)` | Quadrant-corrected right ascension | degrees | RA before final normalization |
| `L₁(29)` | Sun right ascension | degrees | Normalized 0–360° |
| `L₁(30)` | Sun declination | degrees | North +, South − |
| `L₁(31)` | Earth–Sun distance | AU | Used for semidiameter and parallax |
| `L₁(32)` | Approximate lunar mean longitude | degrees | Used in the nutation calculation |
| `L₁(33)` | Nutation in longitude | degrees | Approximate Δψ |
| `L₁(34)` | Greenwich mean sidereal time, raw | degrees | Before normalization |
| `L₁(35)` | Greenwich mean sidereal time | degrees | Normalized 0–360° |
| `L₁(36)` | Greenwich apparent sidereal time, raw | degrees | GMST plus equation-of-equinoxes correction |
| `L₁(37)` | Greenwich apparent sidereal time | degrees | Normalized 0–360° |
| `L₁(38)` | Sun GHA, raw | degrees | GAST − right ascension |
| `L₁(39)` | Sun GHA | degrees | Normalized 0–360° |
| `L₁(40)` | Local hour angle, raw | degrees | GHA + signed longitude |
| `L₁(41)` | Local hour angle (LHA) | degrees | Normalized 0–360° |
| `L₁(42)` | Raw `sin(Hc)` | dimensionless | Calculated-altitude inverse-sine argument before clamping |
| `L₁(43)` | Calculated altitude Hc | degrees | Geometric calculated altitude of Sun centre |
| `L₁(44)` | Azimuth numerator | dimensionless | `sin(LHA)` |
| `L₁(45)` | Azimuth denominator | dimensionless | Intermediate used to determine azimuth and quadrant |
| `L₁(46)` | Preliminary azimuth angle | degrees | Arctangent result before quadrant correction |
| `L₁(47)` | Quadrant-corrected azimuth angle | degrees | Intermediate azimuth |
| `L₁(48)` | Navigational azimuth, raw | degrees | Intermediate after conversion to navigational convention |
| `L₁(49)` | Zn | degrees | Final normalized azimuth, 0–360° |
| `L₁(50)` | Hs | degrees | Sextant altitude converted from `I + J/60` |
| `L₁(51)` | Index correction | degrees | Signed; derived from `L` |
| `L₁(52)` | Dip | degrees | Positive magnitude subsequently subtracted from Hs |
| `L₁(53)` | Ha after index correction and dip | degrees | Apparent limb altitude before refraction correction |
| `L₁(54)` | Bennett base refraction | arcminutes | Base atmospheric-refraction value |
| `L₁(55)` | Bennett refinement term | arcminutes | Small residual correction |
| `L₁(56)` | Refined standard refraction | arcminutes | `L₁(54) + L₁(55)` |
| `L₁(57)` | Pressure/temperature refraction factor | dimensionless | Scales refraction for entered pressure and temperature |
| `L₁(58)` | Actual refraction correction | arcminutes | Refraction for entered pressure and temperature |
| `L₁(59)` | Actual refraction correction | degrees | `L₁(58) / 60` |
| `L₁(60)` | Altitude after refraction correction | degrees | Limb altitude with refraction removed |
| `L₁(61)` | Sun semidiameter | degrees | Derived from Earth–Sun distance |
| `L₁(62)` | Signed semidiameter correction | degrees | Positive lower limb; negative upper limb |
| `L₁(63)` | Sun-centre altitude after SD | degrees | Altitude after semidiameter correction |
| `L₁(64)` | Parallax in altitude | degrees | Solar parallax corrected for distance and altitude |
| `L₁(65)` | Observed altitude Ho | degrees | Final corrected observed altitude of Sun centre |
| `L₁(66)` | Signed intercept | nautical miles | `60 × (Ho − Hc)`; positive = To, negative = From |
| `L₁(67)` | Intercept magnitude | nautical miles | Absolute value of `L₁(66)`; value displayed by SUNSIGHT |
| `L₁(68)` | Unused | — | Current SUNSIGHT does not write this element; its value is not meaningful |
| `L₁(69)` | Raw declination inverse-sine argument | dimensionless | `sin(obliquity) × sin(apparent longitude)` before numerical protection |
| `L₁(70)` | Protected declination inverse-sine argument | dimensionless | `L₁(69)` clamped to the valid range −1…+1 |
| `L₁(71)` | Protected Hc inverse-sine argument | dimensionless | Copy of `L₁(42)`, clamped to −1…+1 before calculating Hc |
| `L₁(72)` | Compact solar-longitude perturbation correction | degrees | Sum of the eight added periodic longitude terms used by v1.1 before apparent solar longitude is formed |

## Notes

The main sight-reduction chain is:

`Hs → index correction → dip → refraction → semidiameter → parallax → Ho`

The final plotting values are:

- `L₁(49)` — Zn
- `L₁(66)` — signed intercept, positive To / negative From
- `L₁(67)` — intercept magnitude

This page documents the memory layout of SUNSIGHT v1.1.0. It is intended for troubleshooting, validation and development; future program versions may change the allocation of scratch locations.
