<!-- TITLE: Radical (machine) -->
<!-- SUBTITLE: A machine running Home Assistant somewhere in QL, possibly by the DMX controller -->

# Radical
Radical is an Intel NUC model NUC5PPYB.

As of this edit, it's running Debian 12 (Bookworm).

[https://www.home-assistant.io/](Home Assistant) (HA) is running on it.  

You can access HA at http://radical:8123.  At the moment accounts are required.  Not sure how to make this friendlier at this point, ask Matt for a login.
There's a generic user: `queeriouslabs` pword is the same as the wifi, which you would know if you were in the space rn, so don't even start asking.  This user is not an admin, which like, would probably be fine.

Please don't ask Matt how to use HA.  Matt doesn't like HA, nor does he wish to "spread the light of knowledge".  HA is there for you to hack on if you wish, and there is volumnous documentation as well as community support elsehwere on the web.  Someone should become an expert on it so Matt doesn't need to learn anything else about it.

If you want ssh access to it, ask someone who has access.  

If you have access, and you want to grant access please:
```bash
$ sudo useradd <newuser>
$ sudo mkdir /home/<newuser>/.ssh
$ sudo nano /home/<newuser>/.ssh/authorized_keys
add a PUBLIC ssh key received from <newuser> into the authorized_keys file
$ sudo chown -R <newuser>:<newuser> /home/<newuser>/.ssh
$ sudo chmod 0600 /home/<newuser>/.ssh/authorized_keys
$ sudo chmod 0700 /home/<newuser>/.ssh
```

At this point, `<newuser>` ought to be able to ssh into the machine using the private key which matches the provided public key.  Assert this.

Add the new user to sudoers.

```bash
$ sudo visudo
Ensure the line below exists in the file, by adding it if it's missing:
<newuser>   ALL=(ALL:ALL) NOPASSWD: ALL
```

assert `<newuser>` can do something like `$ sudo ls` without the shell complaining.

If these instructions are wrong please fix them or note what's wrong or whatever.