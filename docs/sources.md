# Sources and calculation references

SUNSIGHT combines a modernized solar ephemeris with standard marine sight-reduction corrections. This page records the principal sources used during development and validation.

## Historical TI-81 program

William S. Murdock, **“Create Your Own Sun-Sight Reduction Program,” _Cruising World_, March 1996, pp. 47–50.**

The four page images are included in `docs/original-cruising-world-1996/` with the original article. Murdock’s TI-81 listing states that the solar almanac was based on B. Emerson, **N.A.A.O. Technical Note Number 47 — Approximate Solar Coordinates**, Her Majesty’s Nautical Almanac Office, November 1978. It also cites Van Flandern and Pulkkinen, **“Low Precision Formulae for Planetary Positions,” _The Astrophysical Journal Supplement Series_, vol. 41, p. 391 (1979)** for conversion of date/time to the J2000 time argument.

The historical article reports 2,259 bytes for the TI-81 program. The present tested TI-84 Plus SUNSIGHT program occupies 6,734 bytes.

## Solar position

Jean Meeus, **_Astronomical Algorithms_**, 2nd ed., Willmann-Bell, 1998.

SUNSIGHT uses Meeus-style formulae for Julian date, geometric mean longitude and anomaly, orbital eccentricity, equation of centre, apparent solar longitude, obliquity, right ascension, declination, Earth–Sun distance, and the sidereal-time path used to obtain GHA.

## ΔT

Fred Espenak and Jean Meeus, **Polynomial Expressions for Delta T (ΔT)**, NASA/GSFC Eclipse Web Site:

https://eclipse.gsfc.nasa.gov/SEcat5/deltatpoly.html

SUNSIGHT uses the published historical piecewise polynomials for its supported 1900–2049 date range. The decimal year is formed as `year + (month - 0.5)/12`, as specified by Espenak and Meeus.

## Atmospheric refraction

G. G. Bennett, **“The Calculation of Astronomical Refraction in Marine Navigation,” _Journal of Navigation_ 35 (1982).**

SUNSIGHT uses Bennett’s apparent-altitude refraction form, with the refinement term and pressure/temperature scaling used in the program. Refraction is applied after index correction and dip.

## Marine sight-reduction corrections

The operational correction sequence is:

`Hs → index correction → dip → refraction → semidiameter → parallax → Ho`

Solar semidiameter is calculated from Earth–Sun distance. Solar parallax in altitude is likewise adjusted for Earth–Sun distance.

## Independent validation

U.S. Naval Observatory, **Celestial Navigation Data for Assumed Position and Time**:

https://aa.usno.navy.mil/data/celnav

The USNO service provides GHA, declination, Hc, Zn and altitude-correction data for a specified assumed position and time. SUNSIGHT’s four historical test cases were compared independently against this service. See `test-cases.md` for the results.

Across cases A–D, the largest differences found were approximately:

- GHA: 0.16 arcminute
- declination: 0.05 arcminute
- Hc: 0.10 arcminute
- Zn: 0.03 degree

USNO’s displayed refraction correction assumes standard atmospheric conditions; SUNSIGHT instead uses the pressure and temperature entered for the sight. Therefore the refraction columns are not expected to be identical for non-standard test conditions.

## TI-84 Plus software and operating system

Texas Instruments, **TI-84 Plus Operating System v2.55MP**:

https://education.ti.com/en/software/details/en/B7DADA7FD4AA40CE9D7911B004B8C460/ti84plusoperatingsystem

Texas Instruments, **TI Connect CE** software and TI-83/84-family documentation:

https://education.ti.com/

The program in this repository was written and tested on the plain monochrome TI-84 Plus.
