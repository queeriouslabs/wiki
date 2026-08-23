<!-- TITLE: Shi Yang -->
<!-- SUBTITLE: A quick summary of Shi Yang -->

# ShiYang
Shiyang is a 8ish core media server sitting somewhere on the wall in the middle room.  The goal is to put some media front end like kodi on it to easier play media on the projector, along with whatever other things people want to do.  There is nothing precsious about this machine other than it ought to stay functional.

## Credentials
The root password is the wifi pasword. 


## History

A motherboard (which is now dead), CPU (Intel I7-4770k) and memory (32GB of DDR3) was left floating around QL for a while.  I (Matt) found it, and coaxed it from not working to working (after frying the bios of the dead motherboard and having to buy a new one).

This is a janky machine.  The CPU has a bad core.  Luckily it has 8, so 7 are usable.  How annoying.  This was the most annoying bring-up I've dealt with.

## Dealing with the bad CPU core
The first issue is booting at all without using the bad core.  This is managed by limiting the cpus on linux command line.

In `/etc/default/grub` the linux command line now has `maxcpus=1` which limits the system to boot with 1 CPU.  The rest of the good CPUs are booted at runtime via a scipt which pokes them in sysfs.

`/etc/default/grub`:
```
GRUB_CMDLINE_LINUX_DEFAULT=""
GRUB_CMDLINE_LINUX="maxcpus=1"
```
Then run 
```
# update-grub
```

Now at boot, only cpu0 is up.

The script `/opt/bin/pokecpus`  boots CPUs 1-2,4-7.  CPU 3 is bad. 

There's a systemd unit file at `/etc/systemd/system/cpu_poke.service` which runs at boot to bring up the good CPUs via that `pokecpus` script.  By the time the `multi-user.target` is up, the cpus will be up as well.  Boot is slower than it could be, and bumping `maxcpus=2` might work, but it's not possible to limit the cpus beyond this on the command line, thus I cannot avoid the bad core.

Note that if you reinstall any operating system, you will absolutely need to disable the bad CPU somehow.  Ideally that's in the bios, but the current bios on the board does not manage that.  If you are installing a linux variant, you will need to edit the cmdline during the bootloader stage of booting, typically GRUB, and by hitting 'e' to edit the boot commands.   If you don't know how to do this, you are a noob, good luck `:^)`

# Core Hardware
- Intel I7-4770k Haswell
- 32 GB DDR3
- HP EliteDesk 800 G1 SFF mainboard
	- This is a highly non-standard mainboard.  Beyond a bunch of minor things, the hole pattern is not standard for a LGA115X heat sink.
	- There's a 3d / laser cut acrylic bracket to adapt the non-standard heatsink holes to the more standard socket LGA115X holes
	- There's a good amount of documentation available (maintenance, manuals, reference manuals)
	- It's corpo non-sense with more options to lock down machines than manage hardware, whatever, my bad, it was $20.

# Peripherals
## Drives
Ideally SDD from golb for os and applications
(eventually) large HDD RAID array w/ replication for media

## Graphics
- GTX 750 
# Environment
- Debian stable
- Xorg
- Gnome

I tried wayland + KDE/plasma and it didn't work well with the projector on boot.  It was super irritating, and I got tired of once again dealing with (wayland || KDE) not working, where-as Xorg + Gnome "just works".   I would like to expierment with having different window systems, DEs, WMs, etc to work to let them live nicely on the same machine would be interesting!  My choices are wholly practical:  This setup worked.  

# Applications
- Deskflow
	- like a remote kvm, compatible with inputLeap and Barrier
- Firefox
	- Well this is installed by default, but I added uBlock origin.

# Quirks
- On install, the audio was going out through the buzzer speaker on the front panel.  Hilarious.  I installed `pipewire-pulse` and `pavucontrol` and used `pavucontrol` to switch the audio sink to the HDMI port, which flows through the projector to the speakers.  This survived a reboot.

