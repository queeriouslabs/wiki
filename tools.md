<!-- TITLE: Tools -->
<!-- SUBTITLE: A brief list of some tools and their status -->

# 3D Printers
## Anycubic Vyper
[Official Anycubic page](https://www.anycubic.com/products/anycubic-vyper)
### Status as of 2023-08-15
Printer is now setup; cura default for the printer works - likely can go faster though.
## Sparkmaker SLA Printer
### Status as of 2019-08-23
Seems to be fully functional, but prints wont stick to the print plate. A new FEP had no effect. It's unclear what the cause of this was. It might have simply been the orientation of the printed part, given it's surface area. The resin is also possibly a little older than is desirable.
### Status as of 2022-12-31
The printer needs a 24V 2A adapter with an appropriate barrel jack whose location is not currently known; if you know, please reach out!

## Creality LD-002R SLA Printer
[Official printer details](https://www.creality3dofficial.com/products/ld-002r-lcd-resin-3d-printer)
### Status as of 2022-12-31
Fully functional; prints well with the default settings defined for it in Lychee Slicer. Still looking for open source alternative.
### Status as of 2023-05-01
Functional; recently ran a successful test with an open source slicing setup: use prusa slicer settings for the original prusa SL1 and post process with uv3dp for ctb version 2 (`uv3dp --progress ./prusa_output.sl1 ./file_for_printer.ctb --version 2 info`).

## Makerbot Replicator 2X
### Status as of 2022-12-31
Printer is turning on but has not been analyzed further.
### Status as of 2023-05-01
Printer does not accept most SD cards; 2GB SDSC cards were acquired in the hopes they may work but we haven't been successful yet. Unclear where the problem lies.

## Monoprice Select Mini (V1)
[manual](https://downloads.monoprice.com/files/manuals/15365_Manual_170509.pdf)
### Status as of 2023-04-29
Printer is leveled and prints successfully.

## Anycubic Kossel Delta Printer
### Status as of 2023-8-17
Work In Progress -- Use With Caution

Note:
The base firmware does not properly use stored z-calibration values after a reboot.

The machine now runs Marlin.  Z-calibration seems quite good, but other tuning steps are needed, as the filament is stringing.
- [Done] ~~PID: https://www.lpomykal.cz/kossel-pid-calibration/ ~~
- [Done] ~~Extruder: https://www.lpomykal.cz/anycubic-kossel-marlin-extruder-calibration/~~
- Flow:  https://www.lpomykal.cz/anycubic-kossel-marlin-flow-calibration/

There's an issue which occurs at the end of a print.  The machine attempts to home the extruder, but only homes one axis at a time, which doesn't work with a delta configuration.  This causes the firmware to throw an error as the end-stops cannot be reached, and the machine halts and beeps.  It's not the end of the world but it sucks.

The latest Cura includes a machine profile for the Anycubic Kossel Linear Plus

### Marlin Compiled Settings
baud (for USB): 250000
version: bugfix-2.1.x
marlin configuration file: delta/Anycubic/Kossel Linear Plus
# Book Scanners
## Czur Book Scanner
### Status as of 2023-04-29
Fully functional.

# CNC Machines
## MPCNC
### Status as of 2023-05-01

Needs to be fully re-assembled and test. More details [here](/tools/mpcnc).

## Laser Cutter
### Status as of 2023-04-29
Works! more details [here](/tools/lasercutter)

## GENMITSU CNC Router PRO Diy Kit
### Status as of 2025-03-21: Works! 

See [here](/tools/genmitsu-3018-pro-cnc) for more details

# Sewing Machines
## Brother SE-600 Digital Sewing and Embroidery Machine
Has many many stitches, great digital instruction, can do CNC embroidery.

### Status as of 2023-05-01

Works! Requires proprietary software to run.

Note: also accepts certain formats from inkstitch (open source) but may jam easily unless care is taken.

## Singer Heavy Duty Model 44S (grey)
Can do ~15 stitches mechanically chosen.

### Status as of 2023-05-01

Works!

## Singer Model 1234 (white)
Can do ~6 stitches mechanially chosen.

### Status as of 2023-05-01

Works!

# DMX Lighting
### DMX Primer
https://www.chauvetlighting.com/downloads/DMX_Primer_rev05_WO.pdf

## Controller
### Lixada DMX Show Designer
https://www.lixada.com/p-l1350us.html

## Fixtures
### Chauvet DJ SlimPAR64
https://www.chauvetdj.com/products/slimpar-64/
2x on top of middle room loft
?? in front
# Electronics
## HP Agilent Infiniium Oscilliscope
### Status as of 2023-10-01
Fixed! It takes a while to boot (~5 min). 

## Hakko FX-888D
### Status as of 2023-08-10
Works!

The UI is confusing.

To chage the Temperature, press and hold the `Enter` button.  
If you press and hold the `Up` Button, you will actually decalibrate the temperature.  Which is very funny, but also makes the device appear broken.
If it's not working well, like it won't heat up and won't take a new temperature, you can perform a factory reset.  
- Turn off the switch
- press and hold both the `up` and `Enter` buttons
- turn on the switch while holding both buttons
- Release both buttons when an `A` appears. This `A` stands for "Asian", and you can press `Up` to select `U` for United States.  

Some YouTube explanation of the above: https://www.youtube.com/watch?v=VxeN9q336Wg

It's really bad UI.  But it's a realy good soldering station.

## Yihua 936B
### Status as of 2023-08-10
Works!  (replaced 907A handle)
# Misc.
## 10-ton Hydraulic Shop Press
### Status as of 2023-05-01

Works!

## US Cutter Vinyl Cutter
### Status as of 2023-05-01

Works! Takes HPGL over serial (USB to serial cable in accessories box).

Inkcut can generate and send the right format if setup appropriately -- something along the lines of the following should  work: Device->Setup, Add, Name="QL US Cutter", Driver="Inkcut Generic Driver", Connection=(some sort of serial setup, defaults to 9600 baud -- details are computer dependent), Protocol->Language=HPGL

## Vacuum Chamber & Pump
### Status as of 2023-05-01

Works!

## Big Red Doorbell Button
Wiring: connct to C10 and R4 (produces an Enter keypress)