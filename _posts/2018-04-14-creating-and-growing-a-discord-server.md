---
title: "Creating and Growing a Discord Server"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - Discord
  - guide 
  - Discord-Bots
---

> This guide is kept up-to-date as Discord and available resources change!

# Creating and Growing a Discord Server
![logo](https://discordapp.com/assets/fc0b01fe10a0b8c602fb0106d8189d9b.png)

## Introduction
Hello! I'm jagrosh#4824! I'm writing this guide to try to help new server owners set up and grow their servers, which is a commonly-requested topic. It's very easy to go about this the wrong way, so it's best to be prepared and make smart decisions so that your community can flourish!

## Background
You might be wondering: why am I qualified to write this guide? Excellent question! Well, I've created several successful Discord servers, including the Monster Hunter Gathering Hall (70,000+ members, game community), a bot support server (7,500+ members), and two bot community servers (25,000+ members and 20,000+ members). I also help moderate several large servers, and I am a Discord partner. Finally, I am very familiar with the technical aspects of Discord, which are useful for setting up servers and permissions.

<!--more-->

# Part 1: Should I make a server?
This is an important question. Just because you _can_ make a server doesn't mean you _should_. When you're making your server, make sure to ask yourself these questions:
* **Is this something that you are passionate about?** Don't make a server just for the sake of making one. You should be highly interested in the topic and want to improve the community for that topic. You should also be knowledgible about the topic and able to help newcomers and experienced members alike.
* **Does this server have one specific topic?** If your server is a "generic gaming server" or "generic public server" or "random server" or "memes" or any variation, then it is not going to grow. Frankly, no one is interested in joining a server that doesn't have a defined topic. If you take a look at the biggest and most-popular servers on Discord, they all have a specific topic, like "Overwatch" or "World of Warcraft Druids" or "Discord API". If you want your server to become popular, you _must_ pick a specific topic. 
* **Do any other servers for this topic exist?** Once you've decided on a topic, you need to figure out if a server for that topic already exists. For example, don't make a server about "League of Legends," because one already exists. **If a server for your topic already exists, you should join the existing server and contribute to the existing community instead of trying to create a new server for the exact same topic!** However, it's possible that there doesn't exist a server for "League of Legends Demacia Lore," so that would be a perfectly-fine topic to create a server for. (If you don't know if a server already exists, see the "Resources" section at the bottom of this document)
* **Does the topic benefit from having a Discord server?** For some topics, there is no benefit to having a Discord server. Discord is great for real-time communication via text and voice. Make sure that the topic is one that can be discussed in these ways.
* **Do you need to own the server?** This is probably the most important question. Obviously, you're here because you want to set up a server, advertise it, and grow a community. The question is, would you be willing to give ownership and all permissions to someone else if it meant that the community would grow better? If you would not be willing to give ownership to improve the community, you need to stop reading this guide right now and delete the server. Servers aren't things to "show off" because they are popular; they are communities of _real people_ that want to communicate, and you need to care more about that community than about who "owns" the  server itself. This is something you _must_ accept if you want to create a community: that if the community would do better without you, you need to be able to give it up to someone who will perform better.

If you've answered these questions according to the guidelines, you're ready to start setting up the server!

# Part 2: Setting up the server
_This section is still in-progress and should just be used as a basic guide_
## Channels
The key to good channel structure is keeping important information easy to find, and categorizing everything as appropriate. An example of a structure for a "Minecraft Redstone" server might be:
```
 ⌵ Information
   # rules
   # announcements
   # contests
 ⌵ General
   # lobby
   # off-topic
   🔊 Voice
 ⌵ Projects
   # survival_redstone
   # creative_redstone
   # command_blocks
   # map_sharing
 ⌵ Mods
   # mod_chat
   # mod_log
```
Tips:
* **Channel Order** - Keep the 'rules' or 'info' channels near the top; remember that when someone first joins the server, they'll see whatever the first visible channel is (unless the invite they join points somewhere else)!
* **Invites** - I normally don't give people the 'Create Instant Invite' permission via role, and instead create a manual override allowing it only for the 'rules' channel. This means that if someone wants to invite their friend to the server, the friend will see the rules channel first!
* **NSFW Channels** - A good rule of thumb is: don't. There _is_ a reason why you might want to create a NSFW channel, and that reason is if the core topic of the server has a NSFW component. For example, some television shows have scenes that might be not appropriate for underage viewers; a NSFW channel would be useful for discussions about these scenes. *Don't make a NSFW channel if it doesn't relate specifically to the server*.

## Roles
* **"Member" Roles** - "Member" roles (or equivalent) can be useful if you want members to agree to a set of rules (usually via a bot command) or if you want to check out people before manually giving them the role and letting them join the server. *DO NOT* have a bot give every single new member a role right when they join. Why? Giving everyone a role prevents some of Discord's useful features from being possible. The most important is the Verification Level. For large servers, it is important to make sure that all users have verified accounts (linked an e-mail to their account) to avoid spam and raids. However, the server's Verification Level does not apply to anyone with a role, so if you give everyone a role when they join, you are essentially setting your server Verification Level to "None" and leaving yourself wide open to all kinds of attacks. Additionally, the "Prune Members" feature becomes useless as you cannot prune members with roles.
* **Staff/Mod Roles** - I often find it useful to have a colorless role that is given to all Staff (regardless of what kind of staff) to keep the sidebar more organized (I make sure the "Display role members separately from online members" is checked for 'Staff' and unchecked for the other roles). Then, each type of staff has a role with a name and color corresponding to the type of staff they are (Moderator, Event Manager, etc).
* **Bot Roles** - *Never give bots more permissions than they need!!* This is extremely important and a mistake that a lot of people make. Remember, if you give a bot a permission, you are effectively giving that permission to _anyone_ with the bot's token. Usually this is just the owner of the bot, but if they are careless and leak their token, it could be anyone. Most bot invite links come with a preset list of permissions, but if you want to add the bot without giving any permissions right away (and giving the permissions manually later), you can remove the `&permissions=NUMBERS` section of the invite link.

# Part 3: Advertising
First of all, I'd like to describe what I mean by advertising. I _don't_ mean trying to get random users to join your server. I know that a lot of people are desparate to increase their member count, but quality is always more important than quantity. You only want people to join if they are actually interested in the server. This will lead to continued success and high-quality discussion. When I discuss advertising, the goal is to make it so that people who are looking for a server about your topic will be able to easily find your server!
* **Listing Sites** - Check out the resources at the bottom of this guide; there are a few server listing sites that I highly recommend. These sites have been curated due to their SEO (search-engine optimization) and ability to lead interested users to the right servers for specific topics.
* **External Outreach** - Look for subreddits/forums/other resources that share the same topic as your Discord server. Make sure to let users know that you've created a Discord server all about the topic that they enjoy! (Make sure to do this politely though; nobody likes someone spamming links!). Depending on the responses, you might need to make some changes on your server if you want the external communities to support you. Do it! It's very important to get the current communities for the topic involved!
* **Don't spam your invite link on random Discord servers!** - This is _extremely_ important. If you just ask random people to join, and they aren't interested in the topic, there is a high chance they will either a) leave or b) troll. You don't want either of these. What you want is for all (or at least most) of your new members to be people that actually care about the topic. Don't be discouraged if it grows slowly at first! It's better to have 10 members that care than 1,000 members that don't.
* **Get Involved with your own server** - Don't step out of the community to try to fill an "owner" role. Just be part of the community, because _the best and most reliable source of advertising is people telling their friends_.

# Part 4: Tips
These are just some generic tips that usually correlate with success.
1. **Don't separate the "Owner" in the member sidebar.** Usually, a role should only be "displayed separately" or "hoisted" if people need to be able to easily see who is in that role. For example, it's usually good to hoist "Moderators" so that someone can easily ping them if needed. However, hoisting roles like "Owner" just looks narcisistic.
2. **Don't use any kind of "levels" or "exp" system.** Don't give points or award roles for chatting. This is the quickest and easiest way to drown out any real conversation. People are much more engaged in a community if every who is talking is talking because they are interested in the server, not just because they want points. If you are having trouble keeping people engaged, hold events that relate to the topic!
3. **Only have as many moderators as the server needs.** It might be tempting to start adding a bunch of moderators as soon as there is some activity, or as soon as the first bad thing happens, but don't be too quick. Make sure that you completely and fully trust your moderators before adding them, and don't add too many. Early on, you probably only need one or two mods just to make sure that you have all timezones covered. A decent estimate for moderator counts is 1 mod per 1000 members, and 1 admin per 10 mods. This varies a _lot_ based on the nature of the server of course.
4. **Do not advertise to random people, nor on random servers, nor reward people for inviting friends.** Unsolicited advertising breaks Discord's [Terms of Service](https://discordapp.com/terms), so if you send random invites, or even have a system that encourages people to do that, you're breaking the ToS and your server and/or account could be shut down! Follow the rules!
5. **Think about why *YOU* would want to join a server.** Don't follow certain practices or add certain things just because you saw someone else do it, do things because they make your server something you want to be a part of! This is something that so many servers mess up; they add bots or certain channels just because they saw another server with them and not because it actually makes the server more enjoyable.


# Resources
## Server Listing Websites
* **https://invite.gg** - This site is great for getting a customized invite link that can easily distinguish your server.
* **https://www.discordservers.com/** - This is likely the most popular listing site, and allows you to provide a small description about your server. This is very useful when people are searching for the topic of your server.
* **https://www.carbonitex.net/discord/servers** - Carbonitex is great for keeping various stats about your server, including members, activity, and messages. The list here is also often used to rank servers by member count.

## Moderation/Management Bots
* **blargbot** - http://blargbot.xyz/ - This bot can be used to customize your server in almost any way you can imagine. It has a strong custom command implementation that lets you make whatever commands your server is going to need. It can log messages and record moderation actions, and even have some basic automoderation if needed.
* **Vortex** - https://github.com/jagrosh/Vortex/wiki - This is a basic moderation and auto-moderation bot. It doesn't require any setup for the basic commands (using native Discord permissions for its checks), and it's easy to set up some basic auto-moderation for preventing spam, advertisements, and raids.
* **Auttaja** - https://auttaja.io/ - Commonly used for it's 'gatekeeper' functionality, which can help with mitigating problem-users from entering your server in the first place.

## Utility/Information Bots
* **spoo.py** - https://bots.discord.pw/bots/109379894718234624 - spoo.py is great for keeping tabs on members. It can remember what names members used to have, when they were last online, and more. 
* **Logger** - https://discord.bots.gg/bots/298822483060981760 - Logger has the capability to log pretty much anything you'd want to in a consistent format.
* **blargbot** - http://blargbot.xyz/ - Similar to its moderation capabilities, it can be used to provide information to your users. You can make it announce joins or leaves, or make tags for common topics.
* **R. Danny** - https://discord.bots.gg/bots/80528701850124288 - Lots of utilities such as tags & reminders; consider this an alternative option for some of the bots already listed.

## Game Bots
Probably not a good idea. You don't need any game bots. Please don't use bots as a means to increase server activity. These bots can be lots of fun, but they are almost never related to the topic of the server.

## Bot Sites
* **https://discord.bots.gg/** - The original bot list. A diverse directory of Discord bots. This site lists almost all publically-hosted bots.
* **https://www.carbonitex.net/discord/bots** - Carbonitex features many bots that have been determined to meet a certain quality standard.


## Other Guides
* **Discord Project** - https://discordapp.com/invite/project - Useful resources for some technical aspects of Discord.
* **Creating a Discord Server** - https://thelatestdiscord.wordpress.com/2018/08/12/creating-a-discord-server/ - Technical guide for how to set up a Discord server, with images!
