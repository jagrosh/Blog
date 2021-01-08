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

<!--more-->

### Bot Verification requires sharing sensitive - and potentially dangerous - documents with Discord
At least in the United States, verification requires either a driver's license or a passport. Both of these are highly sensitive documents that are extremely dangerous in the hands of bad actors. Both of these documents are common targets for identity theft. A driver's license as a very dangerous piece of documentation to share, and it is often recommended to only share it with government officials or when required by law. See these sources for more information: [1](https://www.idtheftcenter.org/can-someone-steal-your-identity-from-your-drivers-license/), [2](https://www.forbes.com/sites/laurenfix/2018/04/17/personal-privacy-of-your-driver-license/), [3](https://www.pcworld.com/article/136120/article.html)

### Unknown Discord employees have access to your documents
From the support article:
```
Who can access the information I submit?
A small number of employees (as in, fewer than ten) who are involved in security and legal will be able to access the information.
```
Unfortunately, this doesn't provide any specific information or names of the employees that have access. "Fewer than ten" does not mean much when there is no way to guess who those "fewer than ten" employees are. Any bad actor working for Discord could theoretically be or become one of those "fewer than ten." There's also nothing that would prevent Discord from changing this policy down the road to include more employees or other people. 

### Other platforms don't require nearly as much risk to make applications
* Twitter - Applying for a developer account requires detailed use-case information about how you plan to use their API, but no personal documents are needed
* Twitch - [tbd]
* GitHub - [tbd]
* Reddit - [tbd]
* Facebook - [tbd]

### Discord shouldn't need this information to prevent abuse
It's well-known that spam-bots (and other malicious bots) plague Discord. Fake clones of GiveawayBot pop up weekly, spamming direct messages with things such as "get nitro for free by adding this bot to your server," and then using those users' naivety to spread to more users and more servers. A verified tick next to a well-known bot's name, as well as limiting unverified bots to 100 servers, _does_ significantly help prevent this kind of thing. Additionally, verifying a bot locks its name, which prevents a bot being verified under a false pretense and then changing appearance to clone another bot. However, this kind of verification should not require sensitive documents from the bot developer. It should be possible to submit an application for verification (to be reviewed by a human) without risking identity theft.  
Additionally, Discord is a modern company with full engineering and trust & safety teams; they should have the means to detect (and iterate their detection of) these extremely-common abuse patterns and stop them programatically. While I'm not claiming that preventing abuse is easy, Discord as a company should have enough resources to work towards preventing it rather than making a blanket rule that prevents anyone who doesn't feel comfortable risking identity theft from hosting a public application.

### If you share your documents, you are at risk for at minimum an entire year
From the support article:
```
How can I delete the information I’ve submitted?
[...] our retention policy is that we'll remove the identification information a year after the bot that it is connected with has been deleted.
```
A lot of policies can change in a year. If Discord makes a change that you don't agree with, even if you immediately delete your bot, you'd still have your identity available to unknown employees at the company for at least a year.

### Summary
The concept of human-reviewed verification is good, but requiring dangerous documents is unnecessary. Other platforms demonstrate examples of verification that don't require risky behavior, and that abuse can be prevented effectively with these systems. Discord provides very little information about who can access your documents (and no information nor guarantees about the future), increasing the riskiness of sharing sensitive documents with the company.

---

### Update
Since originally writing this article, Discord reached out to me about the verification process, and we found a compromise that enabled me to verify my bots. Essentially, the only data that was needed was real name, birth date, and current address. While I'm sure that there are still many bot devs that feel that this is still too intrusive, this is certainly much better (from an identity theft standpoint) than providing unmodified scans of the raw documents. If you are in the situation where you are not comfortable sending the documents as-is, but are still comfortable with sharing the aforementioned info, consider reaching out to Discord support about this as an alternative verification method.
