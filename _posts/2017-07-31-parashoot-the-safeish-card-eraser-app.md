---
layout: post
title: "Parashoot – The safe(ish) card eraser app"
date: 2017-07-31T13:54:18+00:00
categories: [commercials, DIT, TV, Workflow]
image: /assets/images/parashoot-the-safeish-card-eraser-app-07bd6-screen-shot-2017-07-31-at-7.33.59-am.png
---

I’ve known about this app for a while and just started using this after I heard about an instance where a loader thought they had a card backed up, erased it in disk utility, and then realized it wasn’t actually backed up. To their credit though, it was a few days old from post and the card slipped through the cracks with downloading (although there should be measures for making sure all footage gets downloaded at the end of the day, but still).

So this prompted me to explore this app and see how it integrates into my on-set workflow…and now I will never use anything else to format cards.

As I’ve stated in the past, the reason why you as the DIT want to format cards and then hand them over to ACs is it states to ACs that the footage has been downloaded and it takes the uncertainty of having them format cards, which could have footage on them (I’ve seen it happen first hand!) and then accidentally formatting mags.

The app is [Parashoot](https://parashoot.kamerawerk.ch/), and it’s awesome!

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-6b3ac-screen-shot-2017-07-31-at-7.33.59-am-1.png)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-6b3ac-screen-shot-2017-07-31-at-7.33.59-am-1.png)

Here’s how it works:

You pop a mag into your card reader and in the system tray is the app, so you don’t actually have to have the app open to use it, it just stays in the system tray (which I really like). It’s the highlighted icon here:

![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-1fd57-screen-shot-2017-07-31-at-7.33.31-am.png)

If this is the first time you’ve run it, or if I presume your backup drive isn’t connected (~~or it’s a new one maybe? I don’t see an option to change this, maybe something in a future update?~~ See below for updated information on this) you’ll get this prompt:

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-b3e65-screen-shot-2017-07-31-at-7.32.54-am-300x115-1.png)](https://dorkinatent.wordpress.com/wp-content/uploads/2020/05/52c05-screen-shot-2017-07-31-at-7.32.54-am.png)

It will prompt you for a destination, and then you select that and you’re good.  For me it’s a RAID that I have set up for this TV show I’m on now.

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-62960-screen-shot-2017-07-31-at-7.33.16-am.png)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-62960-screen-shot-2017-07-31-at-7.33.16-am.png)

Then from the drop down menu from the task bar, you select the “Erase XXX” option.

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-ea1dd-screen-shot-2017-07-31-at-8.59.03-am.png)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-ea1dd-screen-shot-2017-07-31-at-8.59.03-am.png)

Then it will give you this prompt (BTW this is a different card because I didn’t take a screenshot of the erase prompt when originally clearing media):

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-ec0c6-screen-shot-2017-07-31-at-7.33.26-am-2.png)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-ec0c6-screen-shot-2017-07-31-at-7.33.26-am-2.png)

To which the system tray will update with this:

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-46634-screen-shot-2017-07-31-at-7.35.41-am.png)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-46634-screen-shot-2017-07-31-at-7.35.41-am.png)

and then finally giving you this prompt:

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-a78a5-screen-shot-2017-07-31-at-7.33.46-am-1-300x131-1.png)](https://dorkinatent.wordpress.com/wp-content/uploads/2020/05/f06fe-screen-shot-2017-07-31-at-7.33.46-am-1.png)

The cool thing here is IF you accidentally format a mag, you can restore it.  Just put the affected mag back in the reader, it will pop up as unreadable (just hit ignore).

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-ba97d-screen-shot-2017-07-31-at-9.39.08-am-300x113-1.png)](https://dorkinatent.wordpress.com/wp-content/uploads/2020/05/de669-screen-shot-2017-07-31-at-9.39.08-am.png)

From the dropdown menu hit Restore Disk 3, and voila, your mag is back in working order.

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-80908-screen-shot-2017-07-31-at-9.40.45-am.png)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-80908-screen-shot-2017-07-31-at-9.40.45-am.png)

If you don’t have it backed up, here’s the error you get (taken from the developer’s screenshots, I didn’t want to chance this at all on my show):

[![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-10cf6-14962660_1330396490303782_4661918961359612556_n.jpg)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-10cf6-14962660_1330396490303782_4661918961359612556_n.jpg) [![]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-de683-14993536_1330396496970448_2134577824589542911_n.jpg)]({{ site.baseurl }}/assets/images/parashoot-the-safeish-card-eraser-app-de683-14993536_1330396496970448_2134577824589542911_n.jpg)

The developer says this is what is going on behind the scenes:

> It creates a statusbar menu with “Erase [YOUR\_CARD]” items. These will run “diskutil partitionDisk diskX MBR FAT32 EMPTY 100%” after ParaShoot has found at least one copy of all your files.
>
> It does only check for filename and file size. No checksums are verified!

This app also integrates with Growl, which I like for notifications.

So there you go.  Stop using DiskUtil for formatting mags.

BTW this will work for Red cameras too, but just make sure you check that the mags don’t revert back to fat32 if you have it set as UDF with the new red firmware.

UPDATE:

Got an email from Ben Hagen, the developer of ParaShoot, and he asked me to add this to the post (I’ll update where it is in the post so this will be redundant):

Changing the backup destination is possible whenever ParaShoot does not find the content of your cards. So if you are on a new project just try to erase as usual and you will get the missing files dialog which will allow you to change the destination. If you ever need to reset it by hand you can run this command from the terminal:  
rm ~/Library/Application Support/ParaShoot/backup\_path

(Yes this should eventually be added to the tool itself.)

Old versions of ParaShoot indeed used the “diskutil partitionDisk” command described at the end of your post. Newer versions erase the card by flipping every bit of the first 2MB (2 \* 1024 \* 1024 bytes) of the card. Every 0 becomes a 1 and every 1 a 0. This destroys all filesystem information in a controlled way and can be easily reversed.

Unfortunately RED cameras will revert back to FAT32 if you format the card on your computer. You can try this when you format them as HFS+ with DiskUtility. Please report this to RED in this way. Other wise they will just blame ParaShoot instead of fixing their bug 😉