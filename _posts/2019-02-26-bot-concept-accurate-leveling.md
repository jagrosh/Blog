---
title: "Bot Concept: Accurate Leveling"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - Discord
  - Discord-Bots
  - development
  - concept
---

## Motivation
I've discussed it [before](/discord/creating-and-growing-a-discord-server/#part-4-tips), but I'm not a big fan of bots that give "levels" or "experience" for sending messages. The most common way of handling this is just to simply give a set (or slightly-varying) amount of points for sending a message. Sometimes there is a cooldown, sometimes there is a minimum message length, sometimes there is a max number of points per day or time period. However, all of these systems suffer from the same problem: *it encourages users simply to send messages, rather than contribute positively to conversations*. I'm sure that some readers out there are thinking "yes, I want as much activity as possible," but from my experience, **not all activity is good activity**. 

<!--more-->

## Goal  
### Do:
~ Encourage users to interact with the server  
~ Encourage users to contribute to conversations with relevant questions and comments  
~ Give proper representation to positive contributors on the server  
### Don't:
~ Encourage users to spam  
~ Encourage users to say irrelevant or 'filler' messages  
~ Encourage users to try to game/cheat the system  
~ Interrupt conversations with "level-up" messages  
~ Interrupt conversations with unecessary reactions or DMs  
~ Require extra work/learning on the user's part  

## Other Social Media
So, how do other social media services solve this problem? Well, let's take a look at a few services that have a comparable problem, and see how they tackle it.  
### Reddit
  While reddit doesn't have the same structure to a normal chatroom, it _does_ have a good way of showing a user's experience, in the form of karma. Karma is gained from users up-voting your messages, and lost from users down-voting your messages (below zero). This becomes a fairly accurate representation of contribution, as meaningful contributions will likely get up-voted and gain karma, while pointless contributions or spam will result in the loss of karma. Additionally, it becomes more valuable to provide useful replies than it does to provide many meaningless replies. In short, karma is a good measure of quality over quantity.  
  Of course, there are flaws to this system as well. For example, the karma system relies on the fact that every message has its own vote counter, which is not very feasible for (and would be obtrusive to) conversations in Discord. Even if some sort of reaction system were used, it would still require extra work by the end users, and they would need to learn how to use this system.
### Facebook, Twitter, and lots more
  Facebook and Twitter both feature a similar system to Reddit: they provide the ability to "like" messages and posts. These two also provide a "share" (or "retweet") functionality to further promote specific messages. Users can "follow" other users to see more posts by those users, which provides a decent metric of who contributes to the site.
  This system requires even more input from users than Reddit, as not only do people need to like/share individual posts, but they need to follow other users to produce the contribution score. This is not very applicable to a chatroom format with conversations.
### League of Legends
  I know what you're thinking: "League of Legends isn't even social media, it's a game!" That's true, but it does have a contribution system worth discussing. At the end of every match, each player is presented with a prompt to award 'honor' to one player on their team (or to nobody). This is nonintrusive during the game, yet still provides a decent indicator of who was friendly and cooperative during the match. Players are incentivized to be pleasant because players that receive a lot of honor get additional badges on their profile (and also because - in general - friendly, cooperative players are more likely to have better teamwork and thus win more).  
  Again, there are issues with this system as well. League of Legends has strongly-defined matches; there is a clear difference between being in a match and being in the post-match lobby. Conversations don't always have as clear of a structure, as particular participants may drop out of a conversation at any point, new participants can join at any point, and conversations can slowly change topic over time without any 'end.' 
### StackExchange
  Calling StackExchange/StackOverflow a 'social media' is a bit of a stretch, but the system used is still related. On SE, users have a reputation score that increases when they perform certain actions (asking or answering questions), and when their questions or answers get upvoted. Additionally, there are badges that users can receive for various actions, such as having a top-voted answer. Having more reputation builds power on the site; minimum reputation thresholds are needed for certain actions (commenting, marking as duplicate, deleting, etc) which helps protect the system from spam and people trying to cheat the system. A combination of reputation and badges is a good indicator of a user's contributions to the site.
  Unfortunately, this system can't be "ported" to Discord, as it works for the question-answer format, not the open chat-room format. Additionally, similar to Reddit, each message would need its own vote-counter to accurately reflect which messages are useful.  

## My Solution
Drawing from things that the provided examples have in common, I've determined some elements that should be present in a solution.  
### Discrete Divisions of Conversation
  The first step in the solution is to divide the ongoing conversation into meaningful chunks. This immediately raises a few issues. Conversations can last for very long periods of time, with the participating members changing throughout. Just because someone starts talking about a topic doesn't mean that they will be active for the entire duration that people are talking about it. Also, conversations can change topics over time, and detecting when the topic has changed is a very difficult thing to tell, especially for a bot.  
  So, instead of trying to break the entire conversation up into chunks, we can split it by each user. When a user sends their first message in a conversation, the bot considers the user to be "active" in the conversation. When they have not sent a message (or been "typing") for more than 10 minutes, the bot will consider them "inactive," and then review their contribution to the conversation while they were active.  
  This solves a few of the goals. Namely, it prevents interrupting the conversation, as it only sends the user notifications _after_ they have finished participating.  
### Message Counting
  At some point, we need to take into consideration how much a person has typed. As already stated, just looking at number of messages sent or length of messages is a poor indication of contribution, but we can use it as a starting point. Specifically, we can look directly at the number of characters they sent, with a few caveats:  
~ Emotes, pings, and channel/role mentions get shortened to their visible text. These things contain IDs that take up 17-20 characters, but aren't actually typed by the user nor are representative of what the user typed.  
~ Some math: the average typing speed is around 40 words per minute. The average typing speed of a user on Discord is likely a bit higher than that, so we'll go with 60 wpm to be safe. The average length of a word is between 4 and 5 characters (varies by language), usually closer to 5. With a space between every word, we're looking at around 6 characters "per word" and 60 words per minute, or 360 characters typed per minute. Of course, since this is a conversation, we'd expect any single user to provide only one-half of the conversation, or less, leaving us at 180 characters per minute. We'll bump that up to 200 characters (to account for edge-cases and the occasional copy-paste) as our upper-limit for how many characters a single user should be able to type when participating in a conversation.  
~ Next, we want deleted messages to count _against_ the total. Whether a message is deleted by a mod or by the user, it likely means that it did not contribute to the conversation, so deleted messages will subtract characters from the total, with an additional 10% taken off. So, if a user sent 3 100-character messages, and deleted one of them, their total would be 300 - (100 * 1.1) = 300 - 110 = 190. (Note: if these 3 messages all happened within 1 minute, using our previous cap would limit the starting number to 200, and then after the subtraction would leave the user at 90).  
~ Finally, a flat amount should be subtracted from every message. This is to subtlely discourage people from breaking up their thoughts into a lot of small messages. This could be 5 or 10 characters per message (one or two words).  
[Sidenote: These numbers and times are estimates and would need to be tested and tweaked if this bot were to actually be developed.]  
### End of Conversation Review
  Alright, so we have a user's messages from a conversation, as well as the time they joined (became active) and left (became inactive). We also have a character-count score for what they typed. What next? Well, we'll want some minimum contribution required to be able to gain "points," such as at least 2 messages and at least 50 characters. If a person reached this threshhold, when they are considered "inactive," the bot will internally award them points for the number of characters typed (after the changes listed in the Message Counting section). If they received some incentive (more on this later), they will receive a DM explaining what they have received.  
  Also, either randomly, or dependent on the amount they contributed, they will be sent a DM with a poll, asking them about the other people they conversed with. They will be given the option to select one other user (or nobody) that they believe contributed positively to the conversation. If they do, both them and the other user will receive bonus points for their effort. This poll can also be ignored with no negative side-effects to earned points, but will reduce the chance of getting such a poll in the future.  
### Incentives
Why should people even try to gain points? The administrators of a server should be able to set incentives at certain point levels, such as:  
~ Access to more channels  
~ Colored roles  
~ Hoisted roles  
~ Roles with additional Discord permissions (External Emojis, Upload Files)    
Some other "custom" incentives might be:  
~ Ability to vote on message deletion (if X many people with this "permission" add a trash-can emoji to a message, delete the message)  
~ Ability to "rep" other users once to give them a point multiplier  
### Self-Moderation
Something that this entire system relies on is that non-contributing messages need to get deleted. Mostly, this can be handled by the moderators and auto-mod bots, but I would strongly-encourage (or require) that the ability to vote on message delete (outlined in Incentives above) be available to users of a certain point count.  
### TL;DR
Basically:  
~ Break 'conversations' up per-user, and do calculation once a user has stopped participating  
~ Count characters sent to determine points, with minimums, maximums, and other requirements. Use these character restrictions to value quality over quantity (like Reddit)  
~ Offer incentives for reaching certain point counts  
~ Occasionally give a survey after a conversation for bonuses (like League of Legends)  
~ With enough points, allow user-based moderation to make sure pointless messages get deleted (like StackExchange)  

## Final Thoughts  
### Do I think this is a perfect system?
No. This is far from perfect, and I'm not even sure a perfect system exists. More importantly, even if this type of bot did exist, I'm not sure it would actually achieve the goals I listed earlier; it might do a bit better than the current "level bots," but I don't know if it would help produce more real, meaningful conversation. If you have ideas for how to improve this system, please leave a comment with your ideas!  
### Am I going to make this bot?
Probably not. I might test something similar on a server at some point, but I don't see myself making any kind of public version of this. I have enough bots to work on, and I'm still not completely satisfied with the solution I've come up with.  
### Can you use these ideas in your own bot?
Go for it! If you like what you've read here and decide to use it, please give me credit for any ideas you use, and [come tell me about it](https://invite.gg/jagrosh)! I'd love to see someone solve this problem!  
