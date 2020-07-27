---
title: "The Future of My Bots"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - discord
  - discord-bots
  - development
---

As I've written in [this post](), I am not currently comfortable with the requirements for verification. As of October 2020, unverified bots will be unable to be added to more than 100 servers, and unverified bots on more than 100 servers will not have access to privileged intents. This means that existing unverified bots (that are already on more than 100 servers) cannot be added to any more servers, and those that rely on certain information from Discord will break completely.

<!--more-->

### GiveawayBot / Frost / 💾❗ / Where's the Party?
These bots don't require privileged intents, so if the verification system does not change, these could still function for the servers that already have them; they just couldn't be added to more servers. 

### Yggdrasil
If the verification requirements don't change, ownership of Yggdrasil will likely change to one of the other developers who is willing to accept the risks of verification. This means that Yggdrasil will likely be unaffected by the change.

### Spectra / Courier Felyne / Phoenix / jagbot
These bots should be mostly unaffected. All except jagbot are already private, and those on more than 100 servers can be pruned down so that they can continue to function correctly.

### Vortex
If verification doesn't change, Vortex will break completely, as it relies on the information from privileged intents to function properly. If this happens, I will create a private and/or paid version of Vortex that will stay on fewer than 100 servers. I _may_ attempt to create a 'lite' version of Vortex to run on the existing Vortex account with limited functionality (due to missing the necessary intents) that would continue to run for servers that already have it.
