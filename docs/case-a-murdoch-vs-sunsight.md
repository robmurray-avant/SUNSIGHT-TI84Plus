# Why Murdoch and SUNSIGHT Differ on Case A

Case A from William S. Murdoch’s 1996 *Cruising World* article is a useful low-altitude regression test because Murdoch’s program and SUNSIGHT v1.1 agree very closely on the Sun’s direction, while the final intercepts differ by a few tenths of a nautical mile.

Murdoch reports:

- Intercept: **11.7191 NM To**
- Zn: **282.7873°**

SUNSIGHT v1.1 gives:

- Intercept: **11.4 NM To** (full-precision value about **11.354 NM To**)
- Zn: **282.8°**

The difference in intercept is about **0.37 NM**. Most of it comes from the different atmospheric-refraction treatment, not from a large disagreement in the computed position of the Sun.

## Case A

Inputs:

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

After index correction and dip, SUNSIGHT’s apparent limb altitude Ha is about **1.7632°**, or **1°45.79′**. This is deliberately a demanding low-Sun refraction case.

## Solar-position comparison

Murdoch’s published Case A values are:

- GHA Sun: **100.3854792°** = **100°23.1288′**
- Declination: **+7.199965171°** = **N 7°11.9979′**
- Computed altitude Hc: **1.490407896°** = **1°29.4245′**
- Zn: **282.7873074°**

SUNSIGHT v1.1 gives approximately:

- GHA Sun: **100°23.079′**
- Declination: **N 7°12.015′**
- Hc: **1°29.463′**
- Zn: **282.787°**

The Hc difference is only about **0.04′**, corresponding to about **0.04 NM** of intercept. The GHA difference is about **0.05′**, and the declination difference about **0.02′**.

So the final intercept difference is not primarily an ephemeris effect.

## Refraction is the larger difference

Murdoch’s published Case A values include:

- Apparent altitude: **1.763207744°**
- Refraction correction: **0.346540626°**

That refraction correction is:

**20.7924′**

Using the Case A pressure and temperature, SUNSIGHT v1.1 calculates about:

**21.0884′**

The difference is therefore about:

**0.296′**

That accounts for most of the roughly **0.37 NM** difference in the final intercept.

Murdoch’s compact pressure/temperature refraction expression is:

```text
.28P/(Q+273)*.0167/tan(W+7.31/(W+4.4))
```

where `W` is apparent altitude, `P` is pressure and `Q` is temperature.

SUNSIGHT’s less compact pressure/temperature refraction expression is:

```text
1/tan(L₁(53)+7.31/(L₁(53)+4.4))→L₁(54)
0-.06sin(14.7L₁(54)+13)→L₁(55)
L₁(54)+L₁(55)→L₁(56)
((N-80)/930)/(1+.00008(L₁(54)+39)(O-10))→L₁(57)
L₁(56)L₁(57)→L₁(58)
L₁(58)/60→L₁(59)
L₁(53)-L₁(59)→L₁(60)
```

where `L₁(53)` is apparent altitude after index correction and dip, `N` is pressure in mb/hPa, `O` is temperature in °C, `L₁(58)` is the refraction correction in arcminutes, and `L₁(60)` is altitude after refraction.

SUNSIGHT uses the Bennett base refraction expression, a small residual correction, and a separate pressure/temperature scale factor.

At ordinary Sun altitudes the two treatments differ very little. Case A makes the difference visible because:

- the Sun is very low
- pressure is relatively high
- temperature is relatively low

Refraction changes rapidly near the horizon, so small differences between models become noticeable in the intercept.

## Why Zn is essentially unchanged

The azimuths are:

- Murdoch: **282.7873°**
- SUNSIGHT v1.1: **282.787°**

They are effectively identical at the precision relevant to plotting.

That is consistent with the main difference occurring in the observed-altitude correction rather than in the sight geometry.

## Which answer should be treated as “correct”?

For Case A, it is better not to describe either final intercept as uniquely correct.

SUNSIGHT v1.1 uses a more elaborate refraction treatment than Murdoch’s compact TI-81 implementation, but at an altitude below about 2° the real atmosphere can depart materially from any standard refraction formula. Surface pressure and temperature do not describe the full vertical structure of the atmosphere.

The practical interpretation is:

> The two programs agree very closely on the Sun’s geometric position. Their small final-intercept difference is mainly a consequence of different standard refraction models applied to an unusually low sight.

That is why SUNSIGHT displays the **LOW SUN / USE WITH CAUTION** warning for Case A.

## Bottom line

For Case A:

- Murdoch intercept: **11.7191 NM To**
- SUNSIGHT v1.1 intercept: **11.354 NM To**, displayed as **11.4 To**
- intercept difference: about **0.37 NM**
- Hc difference: about **0.04′**
- Murdoch refraction: about **20.792′**
- SUNSIGHT v1.1 refraction: about **21.088′**
- refraction-model difference: about **0.296′**
- Zn: essentially identical at **282.8°**

Case A therefore remains a useful hardware regression test, but it is also a reminder that very-low-altitude sights are dominated by refraction uncertainty rather than ephemeris precision.
