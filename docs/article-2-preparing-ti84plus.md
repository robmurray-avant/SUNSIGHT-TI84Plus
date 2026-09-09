# The $40 Celestial Navigator, Part II
## Turning a used TI-84 Plus into emergency navigation gear

*By Rob Murray*

So you have decided that your emergency navigation inventory is incomplete without a calculator last seen in a high-school backpack.

Excellent.

Here is how I set up a plain **TI-84 Plus** for SUNSIGHT.

## Buy the boring one

You want the plain monochrome **TI-84 Plus**.

It should say exactly that on the front.

Not Silver Edition. Not Gold. Not CE. Not Python.

The original black-and-white TI-84 Plus is common on Facebook Marketplace and similar used markets.

Before buying, turn it on and test the screen and keys. Check the USB socket. Most importantly, open the battery compartment and look for corrosion.

Battery leakage is the natural predator of elderly electronics.

## Replace every battery

Once you own it, replace **all the batteries**, regardless of what the seller tells you.

That means the four AAA main cells and the small silver-oxide backup battery.

The calculator may have been sitting in a drawer since Stephen Harper was prime minister. There is no prize for discovering exactly how old its batteries were.

For long-term onboard storage, good low-self-discharge **NiMH** AAA rechargeables are a sensible option. IKEA LADDA cells are one example. I prefer to store the four main cells **out of the calculator**, charged and immediately beside it, rather than trust any battery chemistry indefinitely inside emergency electronics.

Install them for the annual check, run the test, then remove them again.

## Check the operating system

On the calculator, check the operating-system version with:

**2nd → MEM → 1:About**

Texas Instruments lists **2.55MP** as the current OS for the original TI-84 Plus. If your used calculator has an older version, update it before installing SUNSIGHT.

TI’s free **TI Connect CE** software handles the computer-to-calculator connection.

Use fresh batteries while updating the operating system. An OS update is not the moment to discover that the batteries supplied by the Marketplace seller were installed during Grade 9.

## Install SUNSIGHT

Connect the TI-84 Plus to the computer with a USB data cable and open TI Connect CE.

The exact tested program source is `SUNSIGHT.txt` in this repository. It is intended for the plain TI-84 Plus and has been tested on that model.

Paste the source into a TI-BASIC program named `SUNSIGHT` using TI Connect CE’s Program Editor, then transfer it to the calculator.

Do not casually improve the punctuation.

During development we discovered that harmless-looking changes involving colons, spaces, list symbols, inverse-trigonometric tokens and minus signs could turn a functioning celestial-navigation program into something capable of declaring 1950 an invalid year.

The source file is therefore deliberately plain and should be transferred as supplied.

## Test it before trusting it

Run historical Case A:

- Date: 8 Apr 1950
- UTC: 18:43:28
- Position: N 62°28.2′, E 000°18.8′
- Hs: 1°38.2′
- Lower limb
- Index error: 10.2′ off the arc
- Height of eye: 2.2 m
- Pressure: 1050 mb/hPa
- Temperature: 2°C

The answer should be:

**11.3 NM To**  
**Zn 282.8°**

If it is not, check what you entered before blaming the calculator.

I learned this twice.

For commissioning, I recommend running all four cases in `docs/test-cases.md`. They exercise north and south latitude, east and west longitude, upper and lower limb, and both index-error directions.

## Store it as emergency equipment

For ordinary marine protection, put the calculator, batteries and a printed test card in a watertight box with desiccant.

If electromagnetic-pulse protection is part of your emergency planning, first put the disconnected calculator in a proper conductive Faraday pouch or metal enclosure, electrically insulated from the conductive shell and with no wires attached. Then put that inside the waterproof box.

I would not call a random biscuit tin “EMP proof.” Shielding quality depends heavily on seams, openings and penetrations. The aim here is reasonable protection for a small disconnected backup, not qualification for NORAD.

## Once a year

Before an offshore season:

Install the batteries. Inspect the contacts. Run Case A. Confirm **11.3 To, Zn 282.8°**. Remove the main batteries again. Put the calculator back in its box.

Ten minutes.

And unlike most marine-electronics maintenance, no sealant is involved.

Hopefully you will never need it.

Which describes some of the best equipment aboard a cruising boat.
