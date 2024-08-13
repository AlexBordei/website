---
title: "A response to Martijn's blog"
date: "2022-08-18"
authors: ["Marek Kraus"]
categories:
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "community"
cover: 
  image: "cover-wider.jpeg"
images:
  - "/blog/images/cover-wider.jpeg"
---

![](/blog/images/cover-wider.jpeg) 

We rarely, if ever, make responses to blog posts or articles. In fact, there is only [one instance](https://www.pine64.org/2020/01/24/setting-the-record-straight-pinephone-misconceptions/) that I can think of when we did so. So then, somewhat uncharacteristically, this is a response post to Martijn Braam’s [blog](https://blog.brixit.nl/why-i-left-pine64/) in which he explains why he left the PINE64 community. Let’s get one thing out of the way first: Martijn has done a lot for mobile Linux and PINE64 - he is a valued contributor and a colleague with a good insight into how PINE64 and the Pine Store Ltd operate. I should add that his opinions are welcome just as they have always been. Finally, there is no denying that his leaving is a significant loss to the project and, on a private level, a sad state of affairs for us in the community. If it wasn’t clear, we really like Martijn. But this isn’t what this blog post is about. Instead, this is a response to the points and concerns Martijn raises. 

A short summary first: Martijn’s blog entry alleges that following PinePhone community editions, and after settling on Manjaro with KDE’s plasma mobile as the default OS, PINE64 and the Pine Store Ltd have sidelined developers from other mobile Linux projects. The argument is made that this has hurt development. The example given in the blog post supposes that the community team and Pine Store employees were firmly intent on removing SPI on the PinePhone Pro and coerced not to ship Tow-Boot. He concludes by saying that we no longer listen to the development community.

But here is the thing, SPI has been included on the PinePhone Pro due to the input from developers and against our initial intent. The talks concerning SPI were tense, as Martijn mentions in the article, in part because we did approach them with a presumption that we’ll inform developers of our plan to drop SPI. I may add that the decision was made among ourselves, without the input of any third parties or partners. The reasoning behind not including SPI on the PCB wasn’t motivated by any single project or outside source - it was based on the fact that for years SPI was largely unused on PINE64 devices. In instances where it was used, it sometimes caused issues, which in turn led to a few support nightmares. I should also mention that SPI has skyrocketed in price at the time and became harder to source; all this, collectively, had us initially pretty firmly determined to drop SPI altogether. And yet, despite this, we agreed to include it on the PinePhone Pro because developers from multiple projects - postmarketOS being one of them - were adamant that it was an absolute necessity. 

We were also convinced to flash the SPI with Tow-Boot on the most recent batch of PinePhone Pro, which was the preferred bootloader of the majority of members in the private discussion group. Moreover, I should add that SPI is present on the Pinebook Pro and there is no need to solder one on. Pinebook Pro’s SPI doesn’t come with a pre-loaded bootloader, but the option to flash it is there for anyone who wishes to do so. As for the reason why Pinebook Pro doesn’t ship with a bootloader on SPI - it isn’t caused by favoritism for a particular group of developers or disregard for good ideas, but rather something more trivial. Namerly, a functional Tow-Boot build for the Pinebook Pro wasn’t available at the time of manufacture and shipping.    

We created a space for development talks to be held (as we always had), there was a lengthy exchange, there was a difference of opinion, we listened to all developers, and the outcome of the discussion changed our mind on the subject of SPI inclusion and Tow-Boot. And to be clear, we listened to different people. Differences of opinion and unwillingness to listen are two different things and cannot be equated.

All this shouldn’t exactly be a surprise to anyone who has ever interacted with us since, on a weekly basis, we talk to people affiliated with different projects (and to those not affiliated with any projects). Over the past month alone we talked with developers from a handful of major Linux projects regarding support for existing and future devices. We are also in constant contact with community contributors working on non-Linux devices - PineTime, PineBuds and the Pinecil V2 being examples of the latter. And, of course, we talk to our core partners too. This, however, has no impact on whether a good idea from a third party gets implemented or not. We always have been open to suggestions and we will keep on listening to input from the community.  

Now, surely there is more that we could have done in the past in the way of supporting development, and undoubtedly there is more we should do in the future. We haven’t delivered on a variety of ideas concerning supporting our development community - the DevZone being a prime example of a crucial system that still needs to be fully implemented (and it will). The DevZone will, among others, be a place where bounties will be offered to all contributors regardless of affiliation. _Mea culpa,_ an argument can be made that in this regard we haven’t done enough in the past year. At the same time, I believe that our track-record of working with the community is such that listing examples of successful ongoing cooperations and of continuous support is unnecessary. 

To sum up this response post; Martijn has his reasons for leaving and we should all respect those. We are also thankful for all the work he, and the entire postmarketOS has, poured into the Linux smartphone space and the PinePhone in particular. That said, we don’t want to leave the claim that we do not listen to our development community unanswered - because it is unfair and demonstrably false. We are not mindless marionettes unable to make up our own minds about what course to pursue either. As a project, PINE64 is not afraid of taking responsibility or admitting to a fault, and surely there are many mistakes that the management of the project has made in the past, but blind favoritism or unwillingness to listen to our community are not on the list.
