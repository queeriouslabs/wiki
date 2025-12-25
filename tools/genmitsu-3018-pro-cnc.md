<!-- TITLE: Genmitsu 3018 Pro Cnc -->
<!-- SUBTITLE: A quick summary of Genmitsu 3018 Pro Cnc -->

# Genmitsu 3018-PRO CNC Router DIY Kit
https://www.sainsmart.com/products/sainsmart-genmitsu-cnc-router-3018-pro-diy-kit

We have a fully assembled one of these, and it looks like it has upgraded steppers and a much beefier spindle.

The spindle appears to be from this kit:
https://www.xinhuangduo.com/en/h-pd-73.html

The driver is the Woodpecker CanxTool
https://himalayansolution.com/product/woodpecker-cnc-camxtool-v3-4

As of 3/21/2025, the board boots to GRBL 1.1f and accepts commands.  

Using the python program bCNC, I was able to home the device and move each stepper and the spindle.  Seems like it's in working condition.  Need to actually mill something and see what happens.

## Power
There are two power supplies, one for the controller and the XYZ motion steppers, and a separate supply for the spindle.  The spindle can run off the 24V supplied by the brick via a connection on the controller.  This is unlikely to be able to maintain cutting speeds on anything except the softest of materials.  This is useful for debugging the machine, though.

### 24V power Brick for XYZ
The XYZ power supply is a a 24V 5A brick and the USB A - USB B mini cable ought to be cable-manged with it.

![Showing Power Socket On Controller Annotated](/uploads/genmitsu/showing-power-socket-on-controller-annotated.png "Showing Power Socket On Controller Annotated")

### Spindle Power supply
The power supply for the spindle Is separate and is controlled via a potentiometer.

## The power button 
![Controller](/uploads/genmitsu/controller.png "Controller")
The power button for the controller needs to be pushed in to turn on the controller.

## How to use
The main goal of CNC machining is to not crash the machine.  Crashing the machine means don't drive the tool bit deep into the material, machine bed, other parts of the machine, or anything else unintended in a way that breaks something.  This can harm the machine, and potentially someone standing near by, casting material or marchine parts around the area at velocity.

You need a way to create G-code for the machine. When you create this G-code, it must not have instructions that crash the machine.  Ideally it will have instructions which create a useful part, but that's not really the main goal.   That's just a side-benefit of not crashing the machine.

CAD programs can take a design and turn it into G-Code.  IF you understand 3d printing, you you understand slicing.  Same idea.  CAM (Computer Aided Manufacturing) is the dicipline related to useing a computer to manufacture something.  It's about modelling a part and then preparing that model, in some way, for machining.  

Paths, or tool paths, are the basic unit of work for CAM.  The goal of using a CAD program to do CAM is to create paths which will not crash the machine.  These paths are in some sense generic: they are 3D movements the machine will make, and in some sense specifc: they use the 3d geometry of the machine, tool bits, and part to exciiting things like drill holes, mill material, and not crash the machine.  

The CAD program will compute the paths and render them into G-Code.

These links cover some basics using FreeCAD, which works. FreeCAD is not necessarily good, nor friendly, but it is free.
[FreeCAD 1.1 tutorial](https://www.youtube.com/watch?v=7nBCaV5J0Ts)

[FreeCAD Path (CAM) workbench](https://www.youtube.com/watch?v=XRNnWAUoXrk)

The second link is for a 3018 specifically, though that is more about the dimensions of the machine, than the specific Genmitsu 3018-PRO.

The above videos will explain what you need to know, in general, to create G-code for the CNC machine.

## Spoilboard
The purpose of a spoilboard is to let you go negative into the work-surface by a small amount. Note that there are screw heads a couple millimeters below the top surface of the spoilboard. Do not hit those.  That counts as crashing the machine.

You do not need more than 1mm of negative z-depth to achieve a through hole or cut.  That's what the spoilboard is for.  It's a consumable, though can last for a few work-pieces while attempting to remain flat.

It's JUST a piece of MDF, so a new one can be cut from cheap MDF.  Keep the hardware (screws, inserts, T-nuts, etc) and a new one can be cut.

![With Spoil Board](/uploads/genmitsu/with-spoil-board.png "With Spoil Board")

