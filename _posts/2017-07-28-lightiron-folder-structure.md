---
layout: post
title: "LightIron Folder Structure"
date: 2017-07-28T22:55:00+00:00
categories: [DIT, Workflow]
tags: [Alexa, apple, dit, film, hashtag?, light iron, lightiron, mac, macos, OSX, prores, workflow]
---

Got a few requests for this little app so here’s the download [link](https://dorkinatent.wordpress.com/wp-content/uploads/2020/05/4d248-lightiron_folder_structure.zip) for it.

So let’s talk about what this is doing exactly.

When you run this app it’s going to prompt you 4 times.

1. For what shoot day it is
2. For your long term storage (for me it’s my RAID)
3. For your local storage (for me it’s a folder on my desktop for the entire show for CDLs / Screenshots / Reports)
4. For your shuttle drive, which should contain everything going to post/editorial/etc.

Here’s how it should look:

![Screen Shot 2017-07-27 at 3.13.58 PM.png](/assets/images/lightiron-folder-structure-b3b12-screen-shot-2017-07-27-at-3.13.58-pm.png)

The actual app on my DIT cart only prompts me twice, once for the day number and once for the shuttle drive (because my raid and desktop folder never changes, but the shuttle drive does). I suppose later on I could have it automatically look for the previous days, assume what day it is based on the previous days number, get that string value and then increase the number by 1 and completely automate the process so I only have to make an input selection once (for day001)  with the option to opt out, but that’s for another time.  Add it to my to-do list!

Quick disclaimer here: The folders aren’t finalized on the shuttle drive (location 3) for a specific reason, it’s missing the DAY\_XXX\_DATE folders for looks, screenshots, and reports.

The reason being is I’ve had instances where after long ass days on a Friday (like 14 hours or more) I’ve looked at the shuttle drive quickly, seen that there was a folder in there, and then completely forget to copy over screenshots/cdls/reports and then I’m screwed for the whole weekend. So yeah I don’t do that anymore.

So what this does is it forces me to copy the files from my desktop folder onto my shuttle drive every single night, which is my way to quickly spot check to make sure EVERYTHING is on the shuttle drive that needs to be (funny enough as I was writing this I totally blanked on including an extra shuttle drive from VFX with our break, and caught it just in time, ha!). And so I physically move it from my desktop, to the shuttle drive for the Reports, Looks, and Screenshots which I take via scopebox and rename within finder.

I know what you’re thinking.  Why not just keep all of that on your RAID or directly onto the shuttle? Why the redundancy?

Well our job as DITs **IS** redundancy and for most TV shows I don’t keep more than 2 weeks of media on my RAID as that shit fills up quick.  AND I have had questions from productions about previous seasons in the middle of the current season (I was asked randomly if we knew what the reference frame of something we did for Odd Mom Out Season 1 was, and lo-and-behold I was able to queue it up fairly quickly).

Also I just like to keep everything local to my machine in the even that I ever need it.  After I wrap a season I compress that show’s folder, encrypt it, and store it away in dropbox in case I ever need to reference it later on. Every job I’ve ever done I have access to (also makes for nice brownie points with DPs who ask you years later if you have reference stills from that movie you did because he/she wants to replicate that look and wants to show a director quickly).

So yeah, that’s why there are folders missing.  Also there’s only ALEXA\_PRORES & WAV on my RAID because that’s all I need on the RAID, as the rest is on my desktop folder (also why there aren’t ALEXA\_PRORES or WAV folders on my desktop folder).  Oh and LOOKS is in lowercase on the shuttle drive because ExD needs it to be.  The shuttle drives kept coming back in lowercase letters so I asked about it and post request it that way so hence why it’s lowercase.

If you want to modify what it says, or add/remove folders, just open automator & then open the file directly via File>Open>LightIron\_Folder\_Structure.

This is a really simple and straightforward app.  I’ve tried other software but wasn’t a fan of them.  I’m learning swift right now so maybe in the future I’ll be able to refine this and make this a better stand alone app that can have different folder structures (as I have different structures for how post houses want them handled).

Cheers!