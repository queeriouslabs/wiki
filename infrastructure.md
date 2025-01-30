<!-- TITLE: Systems & Infrastructure -->

If you have a question / concern about anything related to this page, feel free to reach out to <sysadmins@queeriouslabs.com>.
# TODO:
* Finish wiki install:
  * create systemd unit file
  * create environment file with google auth credentials
  * copy config file to ansible
  * see if we can get websockets working
* move secrets to ansible-vault
* move discourse over to tachikoma (r)
* change DNS registrar to google domains

# Access
For details of who has access to what, please see the [Access & Responsibilities](/organization/access) page.

Access Control is managed with 13.65 MHz static ID Mifare Classic compatible tokens.


# GSuite
We have a free GSuite account, that we use for email, groups, calendars, drive, google cloud platform etc etc...

We try to provision as much access as possible using groups, primarily the <members@queeriouslabs.com> group, which will be kept up to date with the list of active members. This simplifies the access control greatly.

Anyone that is given admin access **must have 2FA enabled on their account**.

# Google Cloud Projects
The GCloud infrastructure is organized into different projects to keep things cleanly separated.

## Core Infrastructure

The Core Infratructure project is for the most essential web infra for Queerious Labs. Personal projects or less important services MUST NOT run under this project.

### VMs
The majority of our VM administration is done through [ansible](https://www.ansible.com/), and configuration is stored on GitHub: https://github.com/queeriouslabs/infrastructure

The one exception to this is the VM that hosts [discourse.queeriouslabs.com](https://discourse.queeriouslabs.com/login), which is currently on Beka's personal VM, and needs to be moved over.

#### Tachikoma (35.212.195.155)
> [Manage](https://console.cloud.google.com/compute/instancesDetail/zones/us-west1-b/instances/tachikoma?project=onyx-glider-237821)

Currently a n1-standard Google Compute Engine VM. All services running on this VM should be set up using ansible, and use systemd unit files to start on boot.

## Periphery Infrastructure

The Periphery Infrastructure project is for unessential web infra for Queerious Labs. Personal projects and less important services MAY run under this project.

### VMs

#### Gynoid (35.238.38.104)
> [Manage](https://console.cloud.google.com/compute/instancesDetail/zones/us-central1-b/instances/gynoid?project=periphery-infrastructure)

Current an f1-micro Google Compute Engine VM. All services running on this VMV should be set up using ansible, and use systemd unit files to start on boot.

# Domain Names
We have 3 domain names -- queeriouslabs.{com,net,org}.

The .com TLD MUST be used exclusively for Core Infrastructure services, while Periphery Infrastructure services MAY be run on .net and .org. The reason for this is that, since Periphery Infrastructure is intended to be more open and experimental, the we open ourselves to a greater risk of cross site scripting, etc. and by using a different domain, cross-domain vulnerabilities won't be as easy to exploit as within-domain vulns.
# DNS
Currently managed by Beka, this should be transferred over to google domains.
# Website (queeriouslabs.com)
> [Source](https://github.com/queeriouslabs/www.queeriouslabs.com)

The main website is a hugo website, hosted on tachikoma, and made available via caddy. Source is available on GitHub: https://github.com/queeriouslabs/www.queeriouslabs.com

## Website Webhooks
> [Source](https://github.com/queeriouslabs/webhooks)

The are webhooks exposed at `queeriouslabs.com/webhooks` that allow us to trigger certain things when we receive HTTP requests. It's currently a small nodejs application that listens to port `3000` and is made available through caddy reverse proxying to the local `3000` port.

Right now, the only webhook is one that triggers the server to run the website [`deploy.sh`](https://github.com/queeriouslabs/www.queeriouslabs.com/blob/master/deploy.sh), which pulls down the latest source code from GitHub and builds the website. We've linked this up with GitHub so that whenever `master` is updated on GitHub, the website updated to reflect that.
# Wiki (wiki.queeriouslabs.com)
Currently a Wiki.js (v1) wiki on tachikoma, listening locally on port `3010`, made available through caddy reverse proxying to this port.

Everyone who has an `@queeriouslabs.com` account should use google to log in, but we can also allow guests to log in using either another google account, or a username/pw.

All the content is synced with the GitHub repo here: https://github.com/queeriouslabs/wiki
# Discourse (discourse.queeriouslabs.com)
Currently hosted on Beka's server, we need to move this over onto queerious labs infrastructure (probably tachikoma), and ensure we back things up properly.