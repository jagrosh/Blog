---
title: "An Intriguing Social Engineering Scam"
excerpt_separator: "<!--more-->"
categories:
  - Discord
tags:
  - discord
  - psa
  - moderation
---

Preface: I describe some tasks in this story that are potentially dangerous; please do not go messing around in devtools without knowledge of what you are doing.

Earlier today, I received a DM from *lost in the clouds*, with just the word "hi". I get tons of these every day, so I didn't even give it a second thought, I just click past it. One minute later, I get banned from the Gorillaz server. I also don't notice this, as I'm in a lot of servers, and that one is quite far down on my list. A few minutes later, I receive a strange DM from *Smithward*. He mentions that he just banned me from the Gorillaz server, but looking at my profile, he's not sure if the report against me is legitimate. He then shows me a (faked) screenshot of me sending a malware executable in DMs (similar in style to the current nitro scams). I confirm that I have never sent such a DM, and he offers to open a group DM with me and the person who accused me. I accept, and I get added to a group with *Smithward* (supposedly the mod who banned me) and *bobboi* (at the time, he had a different username, and at some point during these events changed it, but I will only use the final name for clarity). After opening the group DM and introduction for its purpose, *bobboi* claims that I definitely sent the contents of the screenshot, and promptly leaves the group DM.

<!--more-->

At this point, I suspect that this *bobboi* person was just trying to frame me, and as soon as he was confronted, decides to leave, as he has no way to back up his story. However, *Smithward* does not take his unsolicited leaving of the group DM as such. Instead, he asks me to screenshare opening my DMs with *bobboi*, just for confirmation. I send him a screenshot of the empty DMs, but he insists on screen sharing. I do a short screen recording, and again, he insists on a screenshare. After carefully checking what I have visible, I share my screen with him, confirming that the DMs are empty. However, this is not enough; he wants me to show my "deleted message history," and asks me to open the dev tools (ctrl-shift-i).

Very, very suspicious. Obviously I am not going to open this during a screen share, and I say this. I end the screen share, and he says that I can find this data by going to the Network tab and copying the HAR of a specific request. I take a look at the data this json contains, and unsurprisingly, it contains the entirety of the headers for the request. This of course includes my user token. I mention to him that I'm not going to share the contents because it contains my token, and he briefly denies that it contains the token, before suddenly closing the group DM and deleting all of the messages that he sent to me.

So... obviously this was a scam.

Anyway, this whole thing still doesn't sit quite right with me. Additionally, I was still banned from the Gorillaz server, and while I'm certainly not active there, it's not great to have a ban sitting there for a false accusation. I ask a friend to find out who the admins of the server are so I can get in contact and maybe clear things up (for them and for me). I contact the admin of the Gorillaz server, informing them that their moderator is conducting a social engineering scam. The admin responds that not only is the user in question not a moderator, but they have never been in the server to begin with! Looking into the ban on the server, he finds the same faked screenshot that *Smithward* sent to me. I enquired about the origin of the screenshot, and he says that I was reported to their server by a user called "*lost in the clouds*." Sound familiar?

The admin and myself each independently reach out to *lost in the clouds* in an attempt to find more information. Upon being messaged, he immediately starts backtracking, claiming that he never reported me, and starts accusing both myself and the admin that we are trying to scam him. When the admin sees what has happened, he unbans me and apologizes for the inconvenience, and I thank him for his help looking into this. I continue digging, and finally *lost in the clouds* tells me that he "was offered 20 usd paypal to report" me. And can you blame him? In his words, "u would have it to mate its free money mate for reporting another mate." Well, regardless of who is to blame, I wasn't finished digging. I ask him who paid him to report me. A lo and behold, the name they offer up is *bobboi*. 

We've pretty much come full circle here. *bobboi* pays *lost in the clouds* to report me from a server, and when that's successful, *Smithward* contacts me about the ban, despite not being a moderator. I of course have no immediate way to confirm, as I can no longer check the moderator list. *Smithward* has me interact with *bobboi* so that it becomes possible to open a DM, and then uses the guise of trying to look at "deleted message history" as an attempt to send my token, which would have full control of my Discord account. Luckily, I'm very knowledgeable about how the dev tools and requests work and stopped the scam in its tracks. However, this was the most roundabout scam I've seen on Discord thus far, and definitely could catch many users. The need to defend one's innocence is a very powerful feeling, and it is understandable that people might make rash decisions in the quest to show that they are not guilty.

Are all of these users the same person? Is *lost in the clouds* just another alt account, or someone innocent that just got mixed up under the temptation of money? The world may never know (although hopefully Discord's Trust and Safety team can figure it out). Either way, I'm curious as to whether I was being targeted specifically, or this is a scam that is being attempted against lots of users. it certainly seems like a lot of work, especially if you end up targeting people that know how Discord works.

That's about it. Special thanks to *Too Many Khaled's* and *Ocean Breeze* for helping me dig into this a bit! Stay safe!
