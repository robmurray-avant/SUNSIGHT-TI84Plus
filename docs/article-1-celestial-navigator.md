# The $40 Celestial Navigator
## From 2,259 bytes on a TI-81 to 6,734 bytes on a TI-84 Plus

*By Rob Murray*

There is something satisfying about navigating an ocean with a calculator whose previous owner probably used it for Grade 11 algebra.

The plain old **Texas Instruments TI-84 Plus** is cheap, tough, battery-powered and common on Facebook Marketplace. With a small program installed, it also makes a remarkably useful dedicated Sun-sight calculator.

Take a sight, enter the date, UTC, DR position, sextant altitude and corrections, and it returns what you actually need:

**11.3 NM To**  
**Zn 282.8°**

No internet. No GPS. No subscription. No nautical almanac.

And the idea is more than 30 years old.

## Murdock did it first

In the early 1990s, William S. Murdock wrote a complete Sun-sight reduction program for tiny Texas Instruments calculators.

His earlier TI-67 version was published in *Practical Boat Owner*. A TI-81 version appeared in *Cruising World* in March 1996 as **“Create Your Own Sun-Sight Reduction Program.”**

The TI-81 program occupied only **2,259 bytes**.

That included the solar ephemeris, sight reduction, corrections and user interaction.

Two thousand two hundred and fifty-nine bytes.

Today, that is roughly enough computer storage for a strongly worded marina Wi-Fi password.

Murdock did this before Google, GitHub, downloadable code libraries or online astronomical calculators. Documentation meant books, technical papers, calculator manuals, magazine articles and correspondence. The *Cruising World* version cites B. Emerson’s *Approximate Solar Coordinates* and Van Flandern and Pulkkinen’s *Low Precision Formulae for Planetary Positions* among its sources.

And he got the whole thing into a TI-81.

That remains the most impressive part of this story.

## TI-81 versus TI-84 Plus

The TI-81 was introduced in 1990 and had only a few kilobytes of user memory, no USB port and no flash archive. Programs were typed in by hand.

The plain TI-84 Plus is still primitive compared with a phone, but beside the TI-81 it is luxurious. It has much more memory, flash storage, USB connectivity and enough speed that we no longer have to count every byte as though provisioning a lifeboat.

That changes the design philosophy.

Murdock had to ask:

**How little astronomy can I get away with and still obtain a useful answer?**

With the TI-84 Plus, we could ask:

**How much better astronomy can we afford while keeping the program simple to use?**

The current SUNSIGHT program occupies **6,734 bytes** on the calculator — almost exactly three times Murdock’s TI-81 program.

He was saving memory.

We are spending it.

## Murdock-era economy versus Meeus-era abundance

The original program used compact, low-precision solar formulae because it had to.

The new TI-84 Plus version replaces that solar ephemeris with calculations based on **Jean Meeus’s _Astronomical Algorithms_**. It also uses Espenak/Meeus historical ΔT polynomials so that the solar calculation can use the appropriate time scale.

This does not make the program smaller.

Quite the opposite.

Murdock’s 2,259-byte program is a masterpiece of compression. The TI-84 Plus simply gives us the luxury of spending more memory and processor time on the astronomy, corrections, error checking and user interface.

The result still appears in a few seconds.

## Why just the Sun?

Because for a cruiser whose celestial-navigation skills have become a little rusty, the Sun is probably the best emergency celestial body there is.

It is difficult to misidentify. It is visible in daylight, when the horizon is usually easiest to see. You do not have to remember which faint star is which while bouncing around at twilight, nor relearn star identification at the same moment the chartplotter has gone dark.

One Sun sight gives a **line of position**.

Two Sun sights separated by time can give a useful **running fix**.

Take a morning sight and plot its LOP. Sail on for a few hours, keeping a reasonable DR. Advance the first LOP by the course and distance travelled. Take another Sun sight later, plot the new LOP, and where the advanced first line crosses the new one is your **Sun-run-Sun fix**.

A useful change in the Sun’s bearing gives a useful crossing angle. The running fix is only as good as the DR between sights — current, leeway and sloppy steering do not disappear because a sextant is involved — but as an emergency technique it is wonderfully simple:

**Find Sun. Shoot Sun. Sail. Shoot Sun again. Plot two lines.**

For someone who learned celestial years ago and has become rusty, that is a much easier skill to recover than a full round of twilight stars.

## What the new program does

The calculator asks for:

**Date and UTC**  
**Position**  
**Hs**  
**Corrections**

For things that commonly cause sign errors, it asks questions instead of expecting the user to remember conventions.

North or South? East or West? Upper or lower limb? Index error on or off the arc?

The calculator deals with the signs.

Internally it calculates the Sun’s position, then applies index correction, dip, atmospheric refraction, semidiameter and parallax. The sailor sees almost none of this.

It returns only:

**Intercept — To or From**  
**Zn**

If the Sun is very low, it warns you. If it is near the zenith, where azimuth becomes touchy, it warns you about Zn.

Otherwise it keeps quiet.

A quality I wish more marine electronics possessed.

## Does it agree with the grown-ups?

We checked four historical examples against the U.S. Naval Observatory’s Celestial Navigation Data service.

Across those four cases, the largest difference in calculated altitude Hc was about **0.1 minute of arc**. Azimuth differed by less than **0.03°**.

That is comfortably below the uncertainty most of us introduce while holding a sextant on a moving yacht.

The detailed figures and all four test cases are included in this repository.

## The difficult part was not astronomy

The mathematics was manageable.

Getting several hundred lines of TI-BASIC through TI Connect and into an elderly calculator was more educational.

Colons behaved differently depending on where they came from.

`L1` was not necessarily `L₁`.

A minus sign could mean subtraction when I wanted negative.

Inverse trig functions required calculator-specific tokens.

A harmless-looking `Pause` needed a trailing space.

At one point the program announced:

**INVALID YEAR 1950**

This seemed unnecessarily judgmental.

Eventually we stopped trying to make the code elegant and concentrated on making it difficult for the calculator to misunderstand.

This is a philosophy familiar to anyone who owns a cruising boat.

## Why carry one?

Nobody needs this while the chartplotter is working.

That is not the point.

Useful offshore redundancy should fail differently from the primary system.

A sextant, UTC watch, paper chart and AAA-powered TI-84 Plus share almost nothing with the boat’s normal navigation electronics.

No GPS receiver. No antenna. No boat power. No network. No internet.

And used TI-84 Plus calculators are cheap enough that dedicating one permanently to the job is hardly extravagant.

Murdock managed the same basic trick more than 30 years ago with **2,259 bytes on a TI-81**.

We now use **6,734 bytes on a TI-84 Plus**.

He was squeezing every last drop from a tiny machine.

We are spending three times the memory on newer astronomy, improved corrections, safeguards and fewer opportunities for the operator to get clever.

The result still does exactly what matters:

You shoot the Sun.

The calculator does the arithmetic.

You draw the line.

A few hours later, you do it again.

And somewhere between those two lines is your boat.

That is quite a lot of navigation for forty dollars.
