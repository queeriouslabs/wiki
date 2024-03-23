<!-- TITLE: Radical Hostname -->
<!-- SUBTITLE: A machine running Home Assistant somewhere in QL, possibly by the DMX controller -->

# Radical
Radical is an Intel NUC model NUC5PPYB.

As of this edit, it's running Debian 12 (Bookworm).

[https://www.home-assistant.io/](Home Assistant) is running on it.  You can access it at http://radical:8123

If you want ssh access to it, ask someone who has acess.

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
