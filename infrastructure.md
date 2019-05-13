<!-- TITLE: Systems & Infrastructure -->

# TODO:
* Finish wiki install:
  * create systemd unit file
  * create environment file with google auth credentials
  * copy config file to ansible
* move secrets to ansible-vault
* move discourse over to tachikoma

# Access
For details of who has access to what, please see the [Access & Responsibilities](/organization/access) page.

# VMs
The majority of our VM administration is done through [ansible](https://www.ansible.com/), and configuration is stored on GitHub: https://github.com/queeriouslabs/infrastructure

The one exception to this is the VM that hosts [discourse.queeriouslabs.com](https://discourse.queeriouslabs.com/login), which is currently on Beka's personal VM, and needs to be moved over.

## Tachikoma (35.212.195.155)
> [Manage](https://console.cloud.google.com/compute/instancesDetail/zones/us-west1-b/instances/tachikoma?project=onyx-glider-237821)

Currently a g1-small Google Compute Engine VM. All services running on this VM should be set up using ansible, and use systemd unit files to start on boot.
# Website (queeriouslabs.com)
## Website Updating Webhook
# Wiki (wiki.queeriouslabs.com)
# Discourse (discourse.queeriouslabs.com)