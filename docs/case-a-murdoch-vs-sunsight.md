# Why Murdoch and SUNSIGHT Differ on Case A

Astute observers will have noticed Case A from William S. Murdoch’s 1996 *Cruising World* article varies in its' answer from SUNSIGHT. Case A is a useful validation case because Murdoch’s program and SUNSIGHT agree very closely on the Sun’s direction, yet they produce noticeably different intercepts.

Murdoch reports:

- Intercept: **11.7191 NM To**
- Zn: **282.7873°**

SUNSIGHT gives approximately:

- Intercept: **11.3 NM To**
- Zn: **282.8°**

At first glance, a difference of about **0.4 NM** in intercept looks larger than expected. The reason is that the two programs differ very little in their computed position of the Sun; most of the difference comes from the atmospheric refraction correction applied to the observed altitude.

## Case A

The inputs are:

- 8 April 1950
- 18:43:28 UTC
- Latitude N 62°28.2′
- Longitude E 0°18.8′
- Sextant altitude 1°38.2′
- Lower limb
- Index error 10.2′ off the arc
- Height of eye 2.2 m
- Pressure 1050 mb
- Temperature 2°C

This is a particularly demanding refraction case because the apparent altitude is only about **1°45.8′** above the horizon.

## The solar calculations are already very close

Murdoch’s published intermediate values for Case A are:

- GHA Sun: **100.3854792°**
- Declination: **+7.199965171°**
- Computed altitude Hc: **1.490407896°**
- Zn: **282.7873074°**

SUNSIGHT gives approximately:

- GHA Sun: **100.3838°**
- Declination: **+7.2006°**
- Computed altitude Hc: **1.4917°**
- Zn: **282.786°**

Expressed in arcminutes, the Hc difference is only about:

**0.08′**

That corresponds to only about **0.08 NM** of intercept.

So the roughly 0.4 NM difference in the final answer is not mainly an ephemeris problem.

## The larger difference is refraction

Murdoch’s published Case A values include:

- Apparent altitude: **1.763207744°**
- Refraction correction: **0.346540626°**

The refraction correction is therefore:

**20.7924′**

SUNSIGHT, using the same pressure and temperature, applies about:

**21.09′**

of refraction.

The difference is approximately:

**0.30′**

That alone accounts for most of the difference in the reported intercept.

Murdoch’s program uses the compact Bennett-style refraction expression:

```text
.28P/(Q+273)*.0167/tan(W+7.31/(W+4.4))
```

where `W` is apparent altitude, `P` is atmospheric pressure and `Q` is temperature.

SUNSIGHT uses a refined Bennett formulation. It first calculates the basic Bennett refraction term, applies Bennett’s residual correction, and then applies a more detailed pressure and temperature adjustment.

At normal Sun altitudes and ordinary atmospheric conditions, the two approaches differ very little.

Case A exaggerates the difference because all three factors are unfavourable:

- the Sun is very low
- pressure is relatively high
- temperature is relatively low

Refraction changes rapidly near the horizon, so a modest difference between correction models becomes visible in the final intercept.

## Why SUNSIGHT uses the newer treatment

Murdoch’s program was remarkably compact and accurate for a TI-81, but it was designed around severe memory and processing limits.

SUNSIGHT has the advantage of more calculator memory and uses later astronomical and refraction methods.

Its solar position calculation is based on more modern algorithms, and its refraction calculation uses a more complete Bennett correction rather than the abbreviated pressure/temperature scaling used in Murdoch’s program.

The important point is that this is not simply extra mathematical complexity for its own sake. Bennett’s refined formulation was developed to reproduce Nautical Almanac-style astronomical refraction more accurately across varying pressure and temperature.

That makes SUNSIGHT’s treatment preferable when the aim is to calculate the standard astronomical correction as accurately as practical on the calculator.

## Why the two programs still agree on Zn

The azimuth is:

- Murdoch: **282.7873°**
- SUNSIGHT: about **282.786°**

They are essentially identical.

That is another indication that the sight geometry is not the source of the intercept discrepancy.

The difference occurs after the geometric sight reduction, when the measured sextant altitude is corrected for atmospheric effects.

## Is SUNSIGHT’s 11.3 NM answer “more correct”?

In the computational sense, **SUNSIGHT uses the more accurate modern model**.

Its ephemeris is generally more accurate than Murdoch’s low-precision solar model, and its refined Bennett refraction treatment is a closer representation of the standard astronomical refraction calculation over varying pressure and temperature.

There is, however, an important practical limitation.

At an altitude below about 2°, real atmospheric refraction can depart noticeably from any standard formula because it depends on the actual vertical temperature structure of the atmosphere, not just the surface pressure and temperature entered into the calculator.

Neither Murdoch nor SUNSIGHT can know that actual atmospheric profile.

So the correct interpretation is:

> SUNSIGHT is using the better computational model, but a very low-altitude sight is inherently less reliable than a higher one.

That is why SUNSIGHT displays its low-Sun caution.

## Bottom line

Murdoch and SUNSIGHT do **not** materially disagree about where the Sun is in Case A.

Their computed altitude differs by only about **0.08′**, and their azimuths are essentially identical.

Most of the approximately **0.4 NM** difference in intercept comes from atmospheric refraction:

- Murdoch refraction: about **20.79′**
- SUNSIGHT refraction: about **21.09′**

SUNSIGHT uses a more complete Bennett pressure/temperature correction and therefore applies about **0.30′** more refraction under the unusual Case A conditions of 1050 mb and 2°C.

That difference is understood, deliberate, and consistent with SUNSIGHT’s use of more modern astronomical and refraction methods.

The remaining caution is physical rather than computational: at such a low Sun altitude, the real atmosphere may not behave exactly like any standard refraction model.
