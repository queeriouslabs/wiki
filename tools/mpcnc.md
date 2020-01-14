<!-- TITLE: Mpcnc -->
<!-- SUBTITLE: A quick summary of Mpcnc -->

# Mostly Printed CNC (MPCNC)

The MPCNC is a built-from-scratch CNC router/mill made using V1 Engineering's 3D Printable design and standard parts. It's capable of cutting most common materials, including wood, aluminum (slowly),
and mild steel (in theory). 

## Mechanical design

The frame serves a dual purpose of both giving the machine the required rigidity and acting as the machine's linear rail. The metal tube looking stuff is US standard 3/4in EMT conduit (23.5mm OD),
which is really super cheap, like $8 for a 10 foot length cheap, but also rigid enough to support the CNC machine's needs.

The base is made from wood, mostly 2x4's with a particleboard top and consumable MDF spoilboard. It has caster wheels on the bottom for moving around the space as needed, as well as on one side so that
the machine can be stood up on it's side and rolled through tight spaces like doorways. There are handles for your convenience, please do not use the frame for a handhold - it's pretty sturdy, but not
so sturdy that you can pick the machine up that way without one of the connectors breaking.

Speaking of breaking things, all the white parts of the machine are 3D printed in PLA using the MPCNC 'Burly' models for 23.5mm tubing. So, if you should happen to accidentally break something, that's
okay! Please just make sure to let one of the members know so that they can 3D print a replacement.

The gantry moves along the conduit with the help of 3D printed carriages that have skateboard bearings bolted on to them, that "hug" the rail and keep the machine rigid. The machine then pulls
itself along the rails using a "belt and pinion" design, where the belt is fixed in place to the corners of the frame, and a pulley attached to the stepper motor pulls the carriage in whatever direction
it needs to go. The belts are the same standard GT2 type commonly used in 3D printers. They're kept at proper tension using the little zip ties attached to the corner of the frame - if the belt feels
loose, just tighten up the zipties and it should be good again!

There's also a dust shoe that is also printed, but not part of the standard design. I found it on thingiverse somewhere, you can probably find it again if you need to.

At the center of the frame is the business end of the machine - a standard, inexpensive Dewalt DW660 hole saw/hand router. The router accepts 1/4in or 1/8in shanks, depending on which collet is currently
installed. This part is moved up and down using a leadscrew instead of a belt, just because a belt would have trouble supporting the weight.

You might also notice little plastic blocks attached at a few points along the belts - these are enstops, that allow the machine to tell when it's travelled as far in one direction as it can go by bumping
against the little endstop switches at each end of the gantry.

That's about all there is to it! All the other mechanical parts are pretty self-explanatory.

## Electronics
The electronics consist of an SKR 1.3 control board, 5 TMC2209 stepper drivers, cheap standard Nema-17 steppers, and a 12v power supply to power it all. The "spindle" is a dewalt DW660.

## Firmware
Firmware is a custom build of Marlin 2.0.x to allow for dual endstops and advanced TMC2209 functionality. Will throw up on git repo at some point soon.

## Software
I believe it should be possible for you to use the sd card to upload gcode, but generally I just control the machine using my laptop and Repetier-Host.

CAM (the CNC equivalent to "slicing" if you're familar with 3D printing terminology) can be done in a number of programs. Estlcam and Fusion 360 are popular but don't support linux - For linux, your best bet is probably Freecad or bCNC, but it's up to you - all the machine cares about is that it recieves valid gcode.

## Operation

(to be continued)