---
layout: post
title: "Working with ARRIRAW – on a Laptop!"
date: 2013-04-22T18:19:19+00:00
categories: [DIT, Major, Workflow]
tags: [Alexa, arri, ARRIRAW, Digital Imaging Technician, dit, filmming, LiveGrade, local 600, macbookpro, major, retina, tom hardy]
---

Note: I’ll be updating this post with various images to make things easier to follow and understand.  Just wanted to get the bulk of this post out there to being with.  Now on to the tech talk.

I’ve just hopped on my first Major Motion Picture called Animal Rescue and have had the pleasure (or tragedy, depending on the situation) of working with codex and ArriRaw from start to finish.  Now I’ve worked with Codex before, but that was on a macpro tower and was just downloading, never actually doing the whole process from start to finish and developing a workflow for it.  Well now that time has come and I have a few thoughts about it.

Arriraw is great if you love the look of the alexa but hate the way the Red functions yet still want raw and a sort-of-3k resolution (the files are 2880×1650 or something of the sort, not quite 3k but close).

I’m working with LiveGrade again (as I love the guys at Pomfort and their support, they’re quick to get back to you (provided you email them before 5pm in Germany time, normally they will email you overnight and you’ll get a response the next morning).  The only difference this time around is I’m using a CDL server to tap directly into the Codex machine and send the CDLs directly to the Codex mag, so that when Post offloads the mag they have my CDLs directly on the mag and there’s no discrepancies between the looks (for the most part, there’s an issue that I can’t figure out which I’ll explain later). Note I should say that post will still need your de-log, as it’s only the CDL that gets applied to the metadata, more on this later.

So far it’s pretty simple yet it does take some terminal skills to SSH directly into the codex to be able to enable the CDL mode from LiveGrade onto the codex.  They have the documentation here.

For some reason my A Camera HDLinkPro is coming up as the B camera slot, which I’m not sure why that happens as I don’t think LiveGrade gives priority to any specific device over the other, it’s just the matter in which they turn on, which is frustrating at the end of the day if you have multiple cameras (I’m constantly switching the labels, would be nice to have some sort of consistency and this also happen to the other programs as per my other DIT friends).

Anyhoo, our workflow is like this:

We have a 512GB Codex mag which holds about 50 minutes of 3k footage (on a 16:9 sensor mind you, if it was 4:3 it would be about 38 minutes, big difference) and we have about 10 32gb cards.  We’re shooting 2k ProRes as a safety in case there are any issues with the codex (which there have been PLENTY). The 2k ProRes holds about 12 minutes of footage, which gives me about 4 full mags on a 512GB Codex SSD.  Obviously for longer takes we have to reload sooner and there might be more than 4 rolls on a mag but it seems to work fine.

Pomfort gave me a beta for the new Silverstack and I have to say I’m liking it so far! I love the silverstack organization and love that I can keep my sound files, SxS and Raw all within the same program and be able to access any of the data at the same time (data in terms of raw data, not playback, there’s no playback support of .ari files in silverstack yet, however you can get GlueTools to preview it).

[![Screen Shot 2013-03-12 at 9.33.13 AM]({{ site.baseurl }}/assets/images/working-with-arriraw-on-a-laptop-screen-shot-2013-03-12-at-9-33-13-am.png)]({{ site.baseurl }}/assets/images/working-with-arriraw-on-a-laptop-screen-shot-2013-03-12-at-9-33-13-am.png)

Since we’re doing 4 rolls per codex mag, I tend to offload each SxS reel in silverstack so I have the ability to track each roll instead of each mag, it makes for keeping track of shots a lot easier (if that’s not too confusing).  If time permits I’ll use Silverstack to offload the Arriraw as well, but almost always I’m pressed for time and so I just revert to using finder for my primary copy.

Before I get too far into the workflow, I wanted to get into what happened in prep and what it is that I’m doing for this movie.

Sixteen19 is handling the post on this movie and all they’re doing for color is taking my CDLs and applying it to the ArriRaw to create the dailies, so everything HAS to be spot on in terms of from on set to post.

What I would recommend, for every job, is to request a specific day of prep to go to post and get your monitors calibrated to their standards (every post house is different FYI).   I took my PVM-2541 to Sixteen19 as well as the DPs on board monitor, which is a TVLogic.  I was able to calibrate the TVLogic as best I could to match Siteen19’s settings as my on set workflow is to send a colored signal back to the DP and AC (as with Codex, both REC OUTs are taken up by the Codex, so I’m forced to take a MON OUT signal set to LOGC, but that’s extremely ugly to look at and to have the director to see) so that the DP can see what I’m doing in realtime color-wise and can comment and give me feedback (as the DP is operating the camera and is unable to sit with me and give me feedback).  I’m also feeding VTR a colored signal and he’s sending that to video village.

So I have a Blackmagic Design Smart Videohub that takes a signal in from each camera (up to 3), sends that to each of my HDLinkPros (again, one for each camera, up to 3), then sends a colored signal to my PVM-2541 and then a log signal to my Flanders so I can monitor the raw image at the same time as I’m setting my LUTs (very handy as I constantly check to see what is clipping and what not).

[![Screen Shot 2013-04-05 at 7.25.58 PM]({{ site.baseurl }}/assets/images/working-with-arriraw-on-a-laptop-screen-shot-2013-04-05-at-7-25-58-pm.png)]({{ site.baseurl }}/assets/images/working-with-arriraw-on-a-laptop-screen-shot-2013-04-05-at-7-25-58-pm.png)

I’m also routing the LUTed signal to my UltraStudio Express in which I can take screenshots of the setups and then display that back onto either monitor so that I can match shots more effectively, all through Media Express.  A really awesome feature to have! It’s been extremely helpful when you’re trying to match a shot from the beginning of the day at the end of the day, or even a few days apart!

Ok, now back to the nitty gritty.

I have a H680 in a Magma 1T express chasis and then using a 1RU raid from OWC as my primary source.  I just have it set up as a RAID1 because I’m only doing 1 copy on set as the codex mags are heading back to post every night for offloading on their end, so essentially my one offload is there in case something horrific happens in transit to the mags (basically as a safety).

So using Silverstack I’m able to backup the SxS cards as well as the sound files and Codex mags, when able.

Other than that, working with Codex is pretty easy once you set it all up, it just takes time to configure and test it out and such.  I’m getting about 300mb/s on transfer rates over thunderbolt to my SAS RAID (which is what the H680 is for, it has 2 ports on it, one for the RAID one for the Desktop Transfer Station). A full mag takes about 30-35 minutes to download once, through finder, and about 55-65 minutes through silverstack with a checksum.  So if you’re only backing up to drives, make sure you have ample time to back up and anren;y going to be stuck having to move locations mid-download (you don’t want to be moving your RAID when the disks are spinning, that’s just asking for corruption to happen).

Anyhoo, hope this is insightful!  I’ll update this more once I have more time to dedicate to it but this is a much needed 7-8 month update since last time.