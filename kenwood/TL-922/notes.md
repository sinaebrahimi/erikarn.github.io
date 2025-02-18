---
layout: default
title: TL-922 notes
---

# Kenwood TL-922

This is both a little repository of information about the Kenwood TL-922
and TL-922A amplifiers that I've found online as well as a list of repairs
I've done to my own unit.

## Overview

## Modifications

Here's a list of modification sites and what seems good/bad.

### W8JI

W8JI has a great analysis of modifications done to a TL-922.  Some are good;
some are bad.

 * <https://www.w8ji.com/tl922_mods_parasitic.htm>

As well as a great writeup on protecting your metering circuit and the reasoning
behind it.

 * <https://www.w8ji.com/metering_amplifier.htm>

The modifications that look sensible here include:

 * Grounding aluminium strap from the VC to the plate chassis
 * Metering circuit protection

However, the suggestion to disconnect the RL-2-1 normally closed contact seems
a bit questionable.  Others have pointed out that the tube should be biased high
when not in use so it doesn't become a white noise generator.  So, perhaps
instead a fuse should go between the filament transformer primary and the
mains supply.

## PA0FRI

Now, if you're interested in where the modifications W8JI disagreed with
came from, here's a great starting point.

 * <https://pa0fri.home.xs4all.nl/Lineairs/TL922/tl-922eng.htm>

There are a bunch of what look like useful and not quite useful modifications here.

The useful modifications:

 * The 1A 250V fuse in the plate B+ supply seems sensible, but a 250v fuse may
   not blow clean (ie, it may blow short.)  It looks like a sensible idea though
   in general and finding a 3500v rated 1A fuse seems .. tricky at best.

 * A 1A slow blow fuse in the filament transformer seems like a good idea.
   It looks like it is supposed to avoid melting the transformer if there's a
   grid-to-filament short.

 * There are disagreements on the value of that glitch resistor in series with
   the B+ supply (10 ohm? 22 ohm?) and whether you should also remove the
   first choke in that circuit.  I need to read more and do a bit more math
   to see what makes sense.

The not-quite-useful modifications:

 * The comments on the grounding wire to ground the variable capacitor
   to the plate seems questionable at best.  It's likely not worth doing.

## Tuning

 * SSB: 1100W is a good target
 * CW: 700W is a good target
 * Idle plate current in transmit for CW is 100mA; SSB is 200mA
 * Tuning for CW: plate current (Ip) < 650mA, grid current (Ig) below 200mA.
 * Dip plate current using tuning.
 * Peak RF output using load; then re-dip plate current.
 * Tuning for SSB: tune for CW, flip to SSB (see below); set CW carrier
   minimum (ie don't dump 100W into the amplifier in SSB mode); increase
   CW carrier until around 1000W-1100W output and tune

Note that so far I've been unable to find an output power peak using load
on 80m and 160m; I may need to re-check the bandswitch and padding capacitors.

Also, don't try to run the amplifier at the load knob at 0 or 1 right now;
it may be too little coupling there and grid current could get a bit hilariously
big and cause things to go "pop!".  It can also lead to higher grid current
than needed and cause the output to go non-linear.  So, don't do it.
Over-couple things a bit and just don't run too much power too long!

## My local repairs

I've done the following to my amplifier.

 * Replaced a shorted plate current meter
 * Diode + capacitor for meter protection
 * 10/15m band mod was performed but the capacitors were on the wrong side of
   the inductor - fixed; 10/15m works fine now.
 * filament fuse
 * low-voltage relay switch kit (ie, so I don't need 100v shorted to ground
   to turn on the amplifier.)

The TODO items.

 * replace the 120v lead to the soft-key board with wire that isn't black!
   (it's all I had on me for 120v!)
 * glitch resistor
 * B+ fuse
 * replacement zener diode, just to be safe
 * (maybe) slow-start kit?
 * (maybe) replace the filter capacitor bank?
 * The switch board controlling the thermal / delay cutoff needs rewiring when
   you switch between 110v and 220v.  This needs to be done!

## PDFs

 * [TL-922A 10 Meter Mod instructions.pdf](TL-922A 10 Meter Mod instructions.pdf)
 * [TL-922OM.pdf](TL-922OM.pdf)
 * [TL-922_Service_Manual.pdf](TL-922_Service_Manual.pdf)

## Links

 * [https://www.w8ji.com/loading_amplifier.htm](https://www.w8ji.com/loading_amplifier.htm)
