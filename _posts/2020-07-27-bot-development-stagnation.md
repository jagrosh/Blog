---
title: "Bot Development Stagnation"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - discord
  - discord-bots
  - development
---

Over the past few months, development of my bots has nearly come to a standstill. Even the changes that have been made have mostly been performance or scaling improvements, with few or no real new front-facing features. There is not just one reason for this, but rather a compounding of several reasons:

<!--more-->

### Time Limitations
As most of you already know, making bots is not my job. While I am lucky that donations from generous individuals cover the majority of the hosting and maintenance costs, bot development ends up being a moderately-costly hobby, in addition to the massive amounts of time it can eat up. Unfortunately, the time here is the limiting resource. I work full-time as a software developer, which means that most days I have minimal time for extraneous activities. Even when I do have time, I am often mentally exhausted from work to the point that working on bots can feel like a chore. 

### Scaling Limitations
As bots become more popular, the ability to quickly add or improve features slows considerably. When a bot is on more servers, its resource usage increases, so more time must be spent optimizing existing features to continue to run quickly. Just because a feature works well when used by one server doesn't mean that it will run flawlessly when used by thousands of servers simultaneously. This can be compounded by limitations imposed on Discord's end, which I will discuss later. Independent of the technical side of scaling, when more people use a bot, more people get used to how a bot works, and so making changes affects more people. Changing the syntax of a command, or removing a feature entirely, will cause more people to be confused or upset when a bot is more popular.

### Support Limitations
I've already discussed how my time is limited, and how making changes and improvements to the bot can be limited by scale, but both of these are also affected by how much support people need. Helping people understand how the bot works and writing documentation to cover more questions takes a lot of time. This is compounded by popularity; as more people use a bot, even if the documentation exists, more people will ask questions. This leads to more time needed to answer these questions, more time needed to improve the documentation in an attempt to reduce questions, and more time needed to try to convince people to read the documentation. All of this time detracts from time that could be spent working on the bot itself. For me specifically, it has nearly gotten to the point that if I spent all of my free time on bot-related things, I would run out of time just answering questions, without even factoring in the time for basic maintenance (like restarting the bot). For people who have asked me questions and haven't gotten a reply, this is likely the reason; I don't have the time to personally answer every question, so I generally only answer the ones that can't be found in the documentation.

### Discord Limitations
Beyond the limitations coming from my end, Discord itself presents a lot of limitations. The first thing many people will think of here is global ratelimits, where bots have a maximum number of "things" per second that they can do. Until a bot is extremely popular (in hundreds of thousands of servers), this is a static number that doesn't change, even when the bot is on more servers (and theoretically doing more "things" total). A bot on one server has the same maximum as a bot on twenty thousand servers. Several features are negatively impacted by this. For example, I recently had to disable voice logging on Vortex, as it was frequently hitting the global ratelimit. It wasn't necessarily any one server causing the problem, but rather just the sum of all servers using the feature ended up exceeding the global limit. However, these ratelimits are not the only limitation that Discord imposes on bots. Unlike regular users, bots cannot "search" channels, which means that any feature that requires searching must either be done by a user manually, or must be limited to a specific subset of messages (as a bot would have to retrieve groups of messages and scan those for the search term). 

### Discord API Changes
Discord has been changing (and breaking) things fairly frequently. These things tend to be most-noticable when they change things that can be exploited, such as changing the mentions system. When a breaking or exploitable change happens, it takes time to refactor and deal with the change. In time-sensitive situations this can be quite stressful as well.

### Number of Bots
Another significant factor in stagnation is simply the number of bots that I maintain. This ends up being compounded by all of the other reasons I've explained thusfar; it takes more time to work on more bots, it takes more time to provide support for more bots, and when Discord's API changes, it takes much longer to update every bot to deal with the changes.

### Upcoming Discord API Changes
