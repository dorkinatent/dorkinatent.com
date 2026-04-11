---
layout: post
title: "The weakest link"
date: 2018-03-30T20:14:34+00:00
categories: [DIT, Workflow]
tags: [Alexa, apple, arri, color, film, gadgets, imac, laptop, mac, mac mini, macbookpro, movies, on set, OSX, RAID, sonnet, SSD, technology, thunderbolt, tv]
---

I’m always looking for ways to improve my on set workflow, and I’m pretty late to the SSD game, but I have an idea about switching everything over to TB3 if the new mac pro eventually goes that route.

Currently I work off a Mac Mini & the thunderbolt 2 world.  For Maisel season 2 we are back to shooting with the Alexa Minis and CFast2.0 cards.  Unfortunately there are no dual CFast2.0 card readers that I know of (could be wrong) and the single card readers are all end of chain, meaning that they only have one TB port and so you have to finish your daisy chain with them.

After using dual card readers on The Good Cop, I won’t ever go back to single card readers.  I use both card readers to primarily queue up offloads.  I always just do one offload at a time because even if you do two offloads at the same time, one offload at a time will be significantly less time due to bandwidth limitations. Now this may be different with the SSD RAID that I just picked up, will be testing and updating this post if I find that to be the case.

Here’s real world examples of why I do one transfer at a time.  The top two are two mags offloaded one then the other, queued up within silverstack. The bottom two are offloading at the same time to the same destination. The two cards with one at a time took about 36 minutes.  With both going at the same time it was about 47 minutes, almost 10 more minutes more for the same amount of data.

![Screen Shot 2018-03-30 at 4.08.49 PM.png](/assets/images/the-weakest-link-4cc16-screen-shot-2018-03-30-at-4.08.49-pm.png)

So with wanting to find a dual card reader that works with CFast2.0, the only option I found was this one:

The kicker with this is that it’s bus powered. That presents a problem for me because I would have to use a dongle to go from TB3 to TB2, and AFAIK you can’t bus power with the dongle due to some weird power tranformations.

I heard from Sonnet directly that this is the case.  Here’s what they said:

> “Thunderbolt 2 does not have enough power to directly connect a Thunderbolt 3 bus-powered device like the CFast 2.0 Pro Card Reader. However, you can connect the CFast 2.0 Pro Card Reader if you have an intermediate Thunderbolt 3 device in the chain that is wall-powered, for example the Sonnet SxS Pro Card Reader.
>
> Thunderbolt 2 Mac—-Apple TB 3 (USB-C) to TB 2 Adapter—-Wall-powered Thunderbolt 3 Device—-CFast 2.0 Pro Card Reader
>
> Note that the Apple Thunderbolt 3 (USB-C) to Thunderbolt 2 Adapter is reversible and will support a Thunderbolt 2 Mac and a Thunderbolt 3 device (as well as a Thunderbolt 3 Mac and a Thunderbolt 2 device).”

This made me think. What can I have that would be TB3 and powered, but I could still connect this card reader to it so it would work with the bus power.

That’s when I found the Akitio Thunder3 Mini Quad: https://www.amazon.com/gp/product/B0713VZW4H/ref=oh\_aui\_detailpage\_o01\_s03?ie=UTF8&psc=1

This would allow me to bus power the card reader and be able to connect via dongle to my mac mini via TB2

PSA: The TB3 to TB2 adapter ONLY works on macOS 10.12 or later

But would it play nice? In fact it would! Here are the speed tests from my 8TB SSD raid vs my 16TB HDD, both in RAID0

![Screen Shot 2018-03-30 at 10.11.16 AM.png](/assets/images/the-weakest-link-40382-screen-shot-2018-03-30-at-10.11.16-am.png)

![Screen Shot 2018-03-30 at 10.10.53 AM.png](/assets/images/the-weakest-link-fe10a-screen-shot-2018-03-30-at-10.10.53-am.png)

That’s almost double the R/W speed for these drives, which is nothing to balk at.

However, when it comes to going home faster at the end of the day, your slowest drive will be your weakest link.

For The Good Cop we only have USB3 readers, and so my bottleneck is limited to whatever the R/W speed of that is, no matter how fast my drives are (interesting thought on this later btw, did a quick test between MD5 & XXHASH and found XXHASH to be only slightly faster).

![Screen Shot 2018-03-30 at 3.19.09 PM.png](/assets/images/the-weakest-link-8b570-screen-shot-2018-03-30-at-3.19.09-pm.png)

You’ll see in a moment that this is reflected as such in my offload tests, although I found something interesting that I can’t quite explain.  My HDD Raid was faster than my SSD raid, by almost a full minute, which I would have expected the opposite. MD5 checksum used below.

![Screen-Shot-2018-03-30-at-12.02.50-PM.png](/assets/images/the-weakest-link-96143-screen-shot-2018-03-30-at-12.02.50-pm-4244735151-1522437939671.png)

And here it is the same result with XXHASH.

![Screen Shot 2018-03-30 at 12.02.50 PM](/assets/images/the-weakest-link-f0942-screen-shot-2018-03-30-at-12.02.50-pm-1-4083634740-1522438023208.png)

More data here:

![Screen Shot 2018-03-30 at 12.05.31 PM](/assets/images/the-weakest-link-9265d-screen-shot-2018-03-30-at-12.05.31-pm.png)![Screen Shot 2018-03-30 at 12.05.36 PM](/assets/images/the-weakest-link-7007a-screen-shot-2018-03-30-at-12.05.36-pm.png)![Screen Shot 2018-03-30 at 12.05.41 PM](/assets/images/the-weakest-link-95b48-screen-shot-2018-03-30-at-12.05.41-pm.png)![Screen Shot 2018-03-30 at 12.05.47 PM](/assets/images/the-weakest-link-daebc-screen-shot-2018-03-30-at-12.05.47-pm.png)

It’s interesting to me that the Average Copy Speed is a good 30MB/s faster on the HDD RAID0 than the SSD RAID0, with the same reader and media being the lowest common denominator.

I’m interested to see what the R/W speeds are for the TB3 Sonnet reader when I start prepping Maisel on the 18th.  Once I am able to get my hands on that and have some more data I’ll report back.