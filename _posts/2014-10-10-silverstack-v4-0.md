---
layout: post
title: "Silverstack 4.0"
date: 2014-10-10T16:08:57+00:00
categories: [DIT, TV, Workflow]
tags: [Alexa, arri, CDL, DaVinci, Digital Imaging Technician, dit, film, LiveGrade, Loader, Media Management, pomfort, SIlverstack]
---

Now that the full version of version 4 is out I figured I would write something about my time with the beta.  I’ve been beta testing the new version of Silverstack for a few months now and I definitely have some thoughts about it, both good and bad.  Here’s what I think:

### User Interface

I really like this new clean interface with v4.  It feels very iOS-like and it’s super easy to navigate, although some things took me a bit of time to figure out.

### New UI:

![Screen Shot 2014-09-30 at 11.37.56 AM](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-11-37-56-am.png)

### Older UI:

[![2](/assets/images/silverstack-v4-0-2.png)](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-11-37-56-am.png)

I really like how it’s all laid out, not very cluttered at all.  I really like having the jobs be in an easy to reach yet not totally distracting on the main layout.  Personally I never use the volumes tab in the old version so I like that the left side is just the folder structure in which I can clearly see how everything is laid out.

I really like how there’s a progress bar at the bottom, which keeps it nice and clean

[![Screen Shot 2014-09-30 at 12.00.52 PM](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-12-00-52-pm.png)](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-12-00-52-pm.png)

The project name and the ability to switch between projects are now displayed at the top:

[![Screen Shot 2014-09-30 at 12.03.19 PM](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-12-03-19-pm.png)](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-12-03-19-pm.png)

And there’s now a section at the bottom right part of the screen which tells you of all your jobs are okay or not, in a very clear and easy color coded section:

[![Screen Shot 2014-10-10 at 12.08.16 PM](/assets/images/silverstack-v4-0-screen-shot-2014-10-10-at-12-08-16-pm.png)](/assets/images/silverstack-v4-0-screen-shot-2014-10-10-at-12-08-16-pm.png)

### XXHash

I really like the performance speed of XXHash, it’s extremely fast in comparison to a MD5 checksum (and honestly I have only had 1 network specifically request MD5 and I was able to convince them to accept XXHash instead as it’s the same algorithm more or less).

Here’s a few examples between MD5 and XXhash from a Echo Express Pro to a USB3 shuttle drive and a 4TB Enterprise drive via OWC SAS RAID connected via Thunderbolt to a Magma 1T

### MD5 offload times (v3)

[![Screen Shot 2014-09-30 at 11.53.23 AM](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-11-53-23-am.png)](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-11-53-23-am.png)

### XXHash offload times (v4)

[![Screen Shot 2014-09-30 at 11.59.38 AM](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-11-59-38-am.png)](/assets/images/silverstack-v4-0-screen-shot-2014-09-30-at-11-59-38-am.png)

It’s pretty significant in the differences (almost half from the previous version of Silverstack).  Here’s a test with the same card using XXHash, MD5, File size verification, and Cascading Copy with XXHash (more on this later) in that order.  Seems like XXHash is slightly faster with version 4 but still, over time it would be a good benefit to have IMO.

[![3](/assets/images/silverstack-v4-0-3.png)](/assets/images/silverstack-v4-0-3.png)

I really like that they implemented File Size verification.  While I don’t recommend using it very often but sometimes it’s a necessity when you’re shooting a TON of footage (or with ArriRaw) and you have to offload cards quickly and efficiently but you don’t want to use finder to drag and drop because you want the organization and ability to generate reports and what not via Silverstack.  That’s when I use file size verification.  It’s fast and still allows you to ingest the media without having to wait longer for the checksum (you can also just import the media into Silverstack without actually using it to do the copy if you want, such as if you’re just sending cards to a post house for offloading and backing up, but if you’re doing the downloading I would avoid using finder at all costs since Silverstack now has this option).

### Cascading copy

[![Screen Shot 2014-10-10 at 11.31.23 AM](/assets/images/silverstack-v4-0-screen-shot-2014-10-10-at-11-31-23-am.png)](/assets/images/silverstack-v4-0-screen-shot-2014-10-10-at-11-31-23-am.png)

I will say right now that I like the idea of cascading copy but I DO NOT recommend using it, EVER.  Here’s why.

I am always an advocate of copying from the source to each destination in every sense of it.  Not only is it faster to copy to 2 sources at once but it also protects you in the long run.  Say you copy CARD01 to SHUTTLE01 and have an error somewhere along the line in the copy for whatever reason, and but you also copy from CARD01 to SHUTTLE02 and everything is fine (which BTW you should ALWAYS QC (quality control) your copies to make sure everything is good).  You can then just redo the copy to SHUTTLE01 and be set.

Now let’s put that same scenario into cascading copy.

You copy CARD01 to SHUTTLE01 and have an error somewhere along the way, then you pull the card as once it’s done copying to SHUTTLE01 the cascading copy starts from SHUTTLE01 to SHUTTLE02 but now you’re copying that error onto SHUTTLE02.  You don’t have time to QC, you send the drive to post, you format the card for re-use and now that error is forever embedded in the footage and you’ve formatted the card, you’re essentially SOL.  It’s a good idea to help with offloading but I don’t like it for that reason that if something happens along the way (which I’ve only had 1 issue with corruption while copying in the 7 years I’ve been a DIT) you’re screwed.

Speaking of formatting cards, I’ll give you this tidbit I’ve been using for a while now:  When shooting with Alexa SXS cards in ProRes (haven’t tried this with Codex yet, but I’m assuming it works as well via VFS) you should wait as long as possible to format your cards AND you as the DIT/Loader should do it on your end via Disk Utility.  Load the card into your system after it’s been downloaded, select it in Disk Utility and go to the ERASE TAB and hit Erase on the card.  It will prompt you with an error, just hit okay.  Now when you pop that card into the camera it will say the card is nor formatted correctly and you should format it in camera, which is what you want.  This way you force the ACs to always have to format the card with that method.  This allows for a few things: A. You cannot accidentally shoot additional footage on the shot cards from the day before B. If you accidentally forget to download footage, or the ACs pull the card and don’t tell you (for whatever reason) it forces them to never accidentally format the shot footage since there would always be a prompt to format the card.  It’s a good failsafe to have and it’s one that I’ve implemented on every job I do and has worked great.  I heard about a job where the DIT pulled the card to check footage and then handed the card back to the loader, who then handed the card to the 1st AC and then he formatted the card out of habit…erasing the first portion of the days work…If you have this method in place then the AC would say “Hey this didn’t prompt me to format the card, is there footage on here?” which would cause the need for someone to say something about it and you don’t lose footage.  It would be a no brainer but shit happens, especially when you’re on hour 16.

Also, I tend to wait until the last possible moment to format the cards, which I tend to do at the beginning of the next day.  The reason for this is the same in which I don’t use cascading copying.  The shot cards are your last defense in case something happens to the shuttle drives and/or your master backup.  It’s always ideal to copy from the source to each destination.  So if something were to happen to the shuttle drive on the way to post and also to your master drive (such as the drive suddenly crashing and dying, which is unlikely but it has happened to me) you have the original media still on the cards.  I tend to wait until the next day because once the dailies are posted (or post emails you saying that everything is backed up properly) you typically know that the footage is all good and you’re safe to format.  As before, it’s the last line of defense, and even though you may never have anything happen to you, if it happens just once in the future a good system of fail safes will save your ass at some point.

Okay, back to silverstack

Everything else is pretty much the same, I haven’t had the chance to test the F65 RAW capabilities OR the LTO functions, although I really like the option of having that in there (considering LTO software is kinda expensive) They added an option of being able to take screenshots throughout the program, which is pretty sweet but I tend to just use Resolve to do all of my screenshots because I almost never use the Arri709 as it just looks terrible.  One thing I would love if Silverstack did was allow you to load a custom 3DLUT into silverstack to view the footage.  I mean Pomfort also makes LiveGrade so it just makes sense to be able to cross use them.  I don’t really use the rendering capabilities out of silverstack because eI again use Resolve to apply the delog and CDLs to footage (as well as sync audio when I do dailies).  I do like the fact that they allowed for the mass selection of clips to be applied for a 2x anamorphic setting (although it would be sweet to be able to apply a project wide desqueeze to the entire project as opposed to each clip individually).

That’s it for now, I may update this post as I find new things within v4.

For those who are using the newest version of Silverstack, what are your thoughts on it?