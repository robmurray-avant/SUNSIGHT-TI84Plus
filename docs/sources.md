# Sources and calculation references

SUNSIGHT combines a modernized solar ephemeris with standard marine sight-reduction corrections. This page records the principal sources used during development and validation.

## Historical TI-81 program

William S. **Murdoch**, **“Create Your Own Sun-Sight Reduction Program,” _Cruising World_, March 1996, pp. 47–50.**

The copyrighted magazine pages are **not** reproduced in this repository. An authorized Google Books copy can be found here:

https://books.google.ca/books?id=yJv58Lx1rhIC&pg=RA3-PA47

For additional historical context on Murdoch's calculator work, see _The Navigator's Newsletter_, Vol. 2:

https://www.starpath.com/foundation/NN-vol-2.pdf

Murdoch's published explanation cites Van Flandern and Pulkkinen, **“Low Precision Formulae for Planetary Positions,” _The Astrophysical Journal Supplement Series_, vol. 41, p. 391 (1979)**, and notes that the formulae were put into the form used by B. Emerson in **N.A.O. Technical Note No. 47 — Approximate Solar Coordinates**, Her Majesty's Nautical Almanac Office, November 1978. Murdoch also cited Montenbruck and Pfleger, **_Astronomy on the Personal Computer_**, Springer-Verlag, 1991.

Murdoch reported a **2,259-byte TI-81 program**. The present tested TI-84 Plus SUNSIGHT program occupies **6,734 bytes on the calculator**. The two calculators use different tokenization and storage architectures, so this is a useful size comparison rather than a precise measure of algorithmic complexity.

## Solar position

Jean Meeus, **_Astronomical Algorithms_**, 2nd ed., Willmann-Bell, 1998.

SUNSIGHT uses Meeus-style formulae for Julian Date, geometric mean longitude and anomaly, orbital eccentricity, equation of centre, apparent solar longitude, obliquity, right ascension, declination, Earth–Sun distance, and the sidereal-time path used to obtain GHA.

## ΔT

Fred Espenak and Jean Meeus, **Polynomial Expressions for Delta T (ΔT)**, NASA/GSFC Eclipse Web Site:

https://eclipse.gsfc.nasa.gov/SEcat5/deltatpoly.html

SUNSIGHT uses the published historical piecewise polynomials for its supported **1900–2049** date range. The decimal year is formed as `year + (month - 0.5)/12`.

## Atmospheric refraction

G. G. Bennett, **“The Calculation of Astronomical Refraction in Marine Navigation,” _Journal of Navigation_ 35 (1982).**

SUNSIGHT uses Bennett's apparent-altitude refraction form, including the refinement term and pressure/temperature scaling used in the program. Refraction is applied after index correction and dip.

## Marine sight-reduction corrections

The operational correction sequence is:

`Hs → index correction → dip → refraction → semidiameter → parallax → Ho`

Solar semidiameter is calculated from Earth–Sun distance. Solar parallax in altitude is likewise adjusted for Earth–Sun distance.

## Independent validation

U.S. Naval Observatory, **Celestial Navigation Data for Assumed Position and Time**:

https://aa.usno.navy.mil/data/celnav

The USNO service provides GHA, declination, Hc, Zn and altitude-correction data for a specified assumed position and time. SUNSIGHT's four historical test cases were compared against this service. See [`test-cases.md`](test-cases.md) for the results.

Across Cases A–D, the largest differences found were approximately:

- GHA: 0.16 arcminute
- declination: 0.05 arcminute
- Hc: 0.10 arcminute
- Zn: 0.03 degree

USNO's displayed refraction correction assumes standard atmospheric conditions; SUNSIGHT instead uses the pressure and temperature entered for the sight. Therefore the refraction columns are not expected to be identical for non-standard test conditions.

## TI-84 Plus software and operating system

Texas Instruments, **TI-84 Plus Operating System v2.55MP**:

https://education.ti.com/en/software/details/en/B7DADA7FD4AA40CE9D7911B004B8C460/ti84plusoperatingsystem

Texas Instruments, **TI Connect CE** software and TI-83/84-family documentation:

https://education.ti.com/

The program in this repository was written and tested on the **plain monochrome TI-84 Plus**.
