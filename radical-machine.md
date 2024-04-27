<!-- TITLE: Radical (machine) -->
<!-- SUBTITLE: A machine running Home Assistant somewhere in QL, probably up in a loft -->

# Radical
Radical is a Lenovo Thinkpad T Series (which one tho)

As of this edit, it's running Debian 12 (Bookworm).

https://www.home-assistant.io/(Home Assistant) (HA) is running on it.  

Inside the space, anyone can access HA at http://radical.queer:8123.  

## Accounts
At the moment accounts are required to use Home Assistant.  HA accounts are separate from machine (e.g. Linux) accounts.  Not sure how to make this friendlier at this point, ask Matt for a login.

There's a generic user: `queeriouslabs` pword is the same as the wifi, which you would know if you were in the space rn, so don't even start asking.  

Please don't ask Matt how to use HA.  Matt begrudingly likes HA, but does not wish to "spread the light of knowledge".  HA is there for you to hack on if you wish, and there is volumnous documentation as well as community support elsehwere on the web.  Someone should become an expert on it so Matt doesn't need to learn anything else about it.

If you want ssh access to it, you can add yourself to the ansible script, and get someone who has access to run it to update the config.  Probably it's someone in the list you added yourself to.  Like you do need to be able to figure this out. It's on the github, sweaty.

If you have access, and you want to grant access please:
```bash
$ sudo mkdir /home/<newuser>/.ssh
$ sudo nano /home/<newuser>/.ssh/authorized_keys
# add a PUBLIC ssh key received from <newuser> into the authorized_keys file
$ sudo chown -R <newuser>:<newuser> /home/<newuser>/.ssh
$ sudo chmod 0600 /home/<newuser>/.ssh/authorized_keys
$ sudo chmod 0700 /home/<newuser>/.ssh
```

At this point, `<newuser>` ought to be able to ssh into the machine using the private key which matches the provided public key.  Assert this.

assert `<newuser>` can ssh in once you place the key and set the permissions.
assert `<newuser>` can do something like `$ sudo ls` without the shell complaining.

If these instructions are wrong please fix them or note what's wrong or whatever.

## Deployment
Radical is managed via ansible and the config is on git: https://github.com/queeriouslabs/radical

Users can be persisted over a rebuild there.  Someone ought to implement key management.

## Backups
Nothing is being automatically backed up yet, due to HA storing credientials.  This can be implemented easily using ansible-vault or similar.
e.g.: https://www.home-assistant.io/integrations/backup/
Set up the backup integration and then encrypt / store the resulting tarball.