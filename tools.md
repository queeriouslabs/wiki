<!-- TITLE: Tools -->
<!-- SUBTITLE: A brief list of some tools and their status -->

# 3D Printers
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
### Status as of 2022-12-31
Unknown

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
## Controller
### Lixada DMX Show Designer
https://www.lixada.com/p-l1350us.html

## Lights
### Chauvet DJ SlimPAR64
https://www.chauvetdj.com/products/slimpar-64/
2x on top of middle room loft
?? in front
# Misc.
## 10-ton Hydraulic Shop Press
### Status as of 2023-05-01

Works!

## US Cutter Vinyl Cutter
### Status as of 2023-05-01

Works! Takes HPGL over serial (USB to serial cable in accessories box).

## Vacuum Chamber & Pump
### Status as of 2023-05-01

Works!