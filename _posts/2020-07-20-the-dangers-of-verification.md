---
title: "The Dangers of Discord Developer Verification"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - discord
  - discord-bots
  - development
---

A few months ago, [Discord announced the bot verification system and requirements](https://blog.discord.com/the-future-of-bots-on-discord-4e6e050ab52e). Since then, they've also added a [support article](https://support.discord.com/hc/en-us/articles/360040720412-Bot-Verification-and-Data-Whitelisting) with more details about it. Unfortunately, the blog post does not discuss the implications of verification, and the support article only touches on it very briefly at the end.

### Bot Verification requires sharing sensitive - and potentially dangerous - documents with Discord
At least in the United States, verification requires either a driver's license or a passport. Both of these are highly sensitive documents that are extremely dangerous in the hands of bad actors. Both of these documents are common targets for identity theft.

### Unknown Discord employees have access to your documents
From the support article:
```
Who can access the information I submit?
A small number of employees (as in, fewer than ten) who are involved in security and legal will be able to access the information.
```
Unfortunately, this doesn't provide any specific information or names of the employees that have access. "Fewer than ten" does not mean much when there is no way to guess who those "fewer than ten" employees are. Any bad actor working for Discord could theoretically be or become one of those "fewer than ten." There's also nothing that would prevent Discord from changing this policy down the road to include more employees or other people. 

### Other platforms don't require nearly as much risk to make applications
* Twitter - Applying for a developer account requires detailed use-case information about how you plan to use their API, but no personal documents are needed
* Twitch - 
* GitHub - 
* Reddit - 
* Facebook - 

### Discord shouldn't need this information to prevent abuse
It's well-known that spam-bots (and other malicious bots) plague Discord. Fake clones of GiveawayBot pop up weekly, spamming direct messages with things such as "get nitro for free by adding this bot to your server," and then using those users' naivety to spread to more users and more servers. A verified tick next to a well-known bot's name, as well as limiting unverified bots to 100 servers, _does_ significantly help prevent this kind of thing. However, 
