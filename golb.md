<!-- TITLE: GOLB (machine) -->
<!-- SUBTITLE: A Raspberry Pi stuck to the wall at QL -->

# GOLB
GOLB is a Raspberry Pi 3B running Debian Bookworm which is in the main room on the wall with the mixers and cables. It has a fileshare accessible via HTTP or Samba; drop whatever files you feel like. It also runs Home Assistant.

Its hostname is `golb`, so it can be accessed via `golb` or `golb.queer` on the local network.

## Fileshare
The fileshare can be accessed at `smb://golb`. Files can also be viewed through the nginx server at `http://golb`.
Ansible setup for fileshare is at https://github.com/nim-ka/golb .

## Home Assistant
The Home Assistant web portal can be accessed at `http://golb:8123`. Username is `queeriouslabs`, and password is the same as the WiFi password.
Ansible setup for Home Assistant is at https://github.com/queeriouslabs/radical .

Please don't ask Matt how to use HA. Matt begrudingly likes HA, but does not wish to "spread the light of knowledge". HA is there for you to hack on if you wish, and there is volumnous documentation as well as community support elsehwere on the web. Someone should become an expert on it so Matt doesn't need to learn anything else about it.

## SSH
Ask Alex or Matt or someone to get a key added.