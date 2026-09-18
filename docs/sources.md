# Sources and calculation references

SUNSIGHT combines a modernized solar ephemeris with standard marine sight-reduction corrections. This page records the principal sources used during development and validation.

## Historical TI-81 program

William S. **Murdoch**, **“Create Your Own Sun-Sight Reduction Program,” _Cruising World_, March 1996, pp. 47–50.**

The copyrighted magazine pages are **not** reproduced in this repository. An authorized Google Books copy can be found here:

https://books.google.ca/books?id=yJv58Lx1rhIC&pg=RA3-PA47

For additional historical context on Murdoch's calculator work, see _The Navigator's Newsletter_, Vol. 2:

https://www.starpath.com/foundation/NN-vol-2.pdf

Murdoch's published explanation cites Van Flandern and Pulkkinen, **“Low Precision Formulae for Planetary Positions,” _The Astrophysical Journal Supplement Series_, vol. 41, p. 391 (1979)**, and notes that the formulae were put into the form used by B. Emerson in **N.A.O. Technical Note No. 47 — Approximate Solar Coordinates**, Her Majesty's Nautical Almanac Office, November 1978. Murdoch also cited Montenbruck and Pfleger, **_Astronomy on the Personal Computer_**, Springer-Verlag, 1991.

Murdoch reported a **2,259-byte TI-81 program**. SUNSIGHT v1.0 occupied **6,761 bytes on the calculator**. SUNSIGHT v1.1 occupies **6,997 bytes on the calculator**; its `.8xp` file is **7,056 bytes**. The two calculators use different tokenization and storage architectures, so byte counts are useful context rather than a precise measure of algorithmic complexity.

## Solar position

Jean Meeus, **_Astronomical Algorithms_**, 2nd ed., Willmann-Bell, 1998.

SUNSIGHT uses Meeus-style formulae for Julian Date, geometric mean longitude and anomaly, orbital eccentricity, equation of centre, apparent solar longitude, obliquity, right ascension, declination, Earth–Sun distance, and the sidereal-time path used to obtain GHA.

Version 1.1 retains that structure and adds eight small periodic corrections to true solar longitude. The terms are derived from Earth-longitude terms in **VSOP87D** and are used only as a compact perturbation correction; SUNSIGHT does not become a full VSOP87D implementation.

Primary VSOP87 reference: P. Bretagnon and G. Francou, **“Planetary theories in rectangular and spherical variables. VSOP87 solutions,” _Astronomy and Astrophysics_ 202 (1988), 309–315.**

## ΔT

Fred Espenak and Jean Meeus, **Polynomial Expressions for Delta T (ΔT)**, NASA/GSFC Eclipse Web Site:

https://eclipse.gsfc.nasa.gov/SEcat5/deltatpoly.html

SUNSIGHT uses the published historical piecewise polynomials for its supported **1900–2049** date range. The decimal year is formed as `year + (month - 0.5)/12`. ΔT is formally **TT − UT1**; SUNSIGHT uses the entered UTC clock as a practical approximation to UT1 and does not require a DUT1 input.

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

The USNO service provides GHA, declination, Hc, Zn and altitude-correction data for a specified assumed position and time. Its time input is UT1, and the public form does not take the observer's pressure and temperature. SUNSIGHT was checked against the four historical Cases A–D and against a separate ten-case 2026–2036 validation suite. The historical USNO comparison therefore uses GHA, declination, Hc and Zn rather than treating USNO's standard-condition refraction as an apples-to-apples check of SUNSIGHT's pressure/temperature correction. See [`test-cases.md`](test-cases.md) for the complete comparison tables and [`case-a-murdoch-vs-sunsight.md`](case-a-murdoch-vs-sunsight.md) for the low-altitude Case A refraction discussion.

Version 1.1 was hardware-tested on a plain monochrome TI-84 Plus with historical Cases A–D. All four passed.

For the separate modern ephemeris comparison, the exact v1.1 formulas and the reconstructed Murdoch article code were run off-calculator against the same ten USNO cases. Over those ten cases:

- SUNSIGHT v1.1 GHA: **0.044′ mean absolute difference**, **0.145′ maximum**
- Murdoch GHA: **0.046′ mean absolute difference**, **0.103′ maximum**
- SUNSIGHT v1.1 declination: **0.032′ mean absolute difference**, **0.063′ maximum**
- Murdoch declination: **0.022′ mean absolute difference**, **0.048′ maximum**

USNO displays GHA and declination to 0.1′, so differences below roughly 0.05′ are at or below the display-resolution floor and should not be used to claim meaningful superiority of one compact algorithm over another.

A separate broad numerical stress test compared v1.0 and v1.1 with Swiss Ephemeris apparent geocentric solar coordinates every two days at 12:00 from 1900 through 2049, 27,394 epochs. Swiss Ephemeris was used as a high-precision numerical reference, **not as USNO**. In that test, GHA RMS error fell from about **0.201′** in v1.0 to **0.059′** in v1.1, and maximum GHA error from about **0.618′** to **0.196′**. Declination RMS fell from about **0.059′** to **0.019′**.

For the modern USNO comparison, the same numerical date and clock time were entered as USNO UT1 and SUNSIGHT UTC. The resulting sub-second time-scale difference is deliberately outside SUNSIGHT's standalone input model.

## TI-84 Plus software and operating system

Texas Instruments, **TI-84 Plus Operating System v2.55MP**:

https://education.ti.com/en/software/details/en/B7DADA7FD4AA40CE9D7911B004B8C460/ti84plusoperatingsystem

Texas Instruments, **TI Connect CE** software and TI-83/84-family documentation:

https://education.ti.com/

The program in this repository was written and tested on the **plain monochrome TI-84 Plus**.
