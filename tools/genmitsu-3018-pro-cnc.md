<!-- TITLE: Genmitsu 3018 Pro Cnc -->
<!-- SUBTITLE: A quick summary of Genmitsu 3018 Pro Cnc -->

# Genmitsu 3018-PRO CNC Router DIY Kit
https://www.sainsmart.com/products/sainsmart-genmitsu-cnc-router-3018-pro-diy-kit

We have a fully assembled one of these, and it looks like it has upgraded steppers and a much beefier spindle.

The driver is the Woodpecker CanxTool
https://himalayansolution.com/product/woodpecker-cnc-camxtool-v3-4

As of 3/21/2025, the board boots to GRBL 1.1f and accepts commands.  

Using the python program bCNC, I was able to home the device and move each stepper and the spindle.  Seems like it's in working condition.  Need to actually mill something and see what happens.

The power supply is a a 24V 5A brick and the USB A - USB B mini cable ought to be cable-manged with it.

## The power button on the driver board is just a white clicky thing and easy to miss.

Hopefully I will bring this up to a usable state.

The spindle appears to be from this kit:
https://www.xinhuangduo.com/en/h-pd-73.html


## How to use
The main goal of CNC machining is to not crash the machine, which means don't drive the bit deep into the material, bed, parts of the machine, or anything else unintended.  This can harm the machine, and potentially someone standing near by casting material or marchine parts around the area at velocity.

You need a way to create G-code for the machine. When you create this G-code, it must not have instructions that crash the machine.  Ideally it will have instructions which create a useful part, but that's not really the main goal.   That's just a side-benefit of not crashing the machine.

You can use an 
