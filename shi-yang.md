<!-- TITLE: Shi Yang -->
<!-- SUBTITLE: A quick summary of Shi Yang -->

# ShiYang
Shiyang is a 8ish core media server sitting somewhere on the wall in the middle room.  The goal is to put some media front end like kodi on it to easier play media on the projector, along with whatever other things people want to do.  There is nothing precsious about this machine other than it ought to stay functional.

## History

A motherboard (which is now dead), CPU (Intel I7-4770k) and memory (32GB of DDR3) was left floating around QL for a while.  I (Matt) found it, and coaxed it from not working to working (after frying the bios of the dead motherboard and having to buy a new one).

This is a janky machine.  The CPU has a bad core.  Luckily it has 8, so 7 are usable.  How annoying.  This was the most annoying bring-up I've dealt with.

## Dealing with the bad CPU core
in `/etc/default/grub` the linux command line now has `maxcpus=1` which limits the system to boot with 1 CPU.  The rest can be booted as runtime via sysfs.

```
GRUB_CMDLINE_LINUX_DEFAULT=""
GRUB_CMDLINE_LINUX="maxcpus=1"
```
Then run 
```
# update-grub
```

There's a script in `/opt/bin/pokecpus` which boots CPUs 1-2,4-7.  CPU 3 is bad. 
There's a systemd unit file at `/etc/systemd/system/cpu_poke.service`
This runs at boot to bring up the good CPUs via the `pokecpus` script.

Note that if you reinstall any operating system, you will absolutely need to disable the bad CPU somehow.  Ideally that's in the bios, but the current bios on the board does not manage that.  If you are installing a linux variant, you will need to edit the cmdline during the bootloader stage of booting, typically GRUB, and by hitting 'e' to edit the boot commands.   If you don't know how to do this, you are a noob, good luck `:^)`

## Core Hardware
Intel I7-4770k Haswell

HP EliteDesk 800 G1 SFF mainboard
- This is a highly non-standard mainboard.  There's a 3d / laser cut acrylic bracket to adapt the non-standard heatsink holes to the more standard socket LGA115X holes

32 GB DDR3

## Drives
Ideally SDD from golb for os and applications
(eventually) large HDD RAID array w/ replication for media

