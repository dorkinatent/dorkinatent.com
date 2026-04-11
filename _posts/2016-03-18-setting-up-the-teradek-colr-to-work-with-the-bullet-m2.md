---
layout: post
title: "Setting up the Teradek COLR to work with the Bullet M2"
date: 2016-03-18T21:24:03+00:00
categories: [DIT, Tier1, TV, Workflow]
tags: [Alexa, arri, CDL, COLR, Digital Imaging Technician, dit, film, LiveGrade, local 600, LUT, nerd, Paralinx, pomfort, Teradek, workflow]
---

I’m currently writing a review on my experiences with the Teradek COLR (will update this post to link to that) but I’ve had some questions about how to set up a network to be able to work with it, and I’ve had some difficult issues with it and have finally settled on how best to set this up so I figured I’d write something up on this.

I’m not going to go into detail about the COLR unit and functions itself, as that will be for the review, as I am mainly focusing on how to set up the COLR network and how to troubleshoot it (and my experiences troubleshooting also).

I’m going to start by suggesting my current setup in which I came to the conclusion of what works for me in my on set setup.  I had a different configuration to start with, and I will go over that later on in case people are having issues with getting a different brand of router to work, however for the purpose of this post this will focus on what I finally got to work with no hiccups.

Before I start, I want to give a big thanks to fellow DIT [Tom Wong](http://thewongcut.com/) for helping me figure a lot of this out.  I had issues out the wazoo and bombarded him with questions, and he really helped me troubleshoot.  Thanks Tom!

Also a slight disclaimer: I suck at IT.  I came to this conclusion based off of what I wanted to accomplish and figured it out on my own.  You may have a better way to do this but this is what worked for me and I just wanted to share my findings.

Also, this setup works on a 2.4GHz frequency.  The reason for that is most video transmitters work on the 5GHz frequency and won’t cause interference with the COLR, in theory.  You can use a 5GHz band if you’d like but I ended up not going that route for this guide as I didn’t want to cause problems with the TX/RX and the COLR.

On to the setup then!

**THE EQUIPMENT**

Feel free to click on each item as I’ve included the links to Amazon, or you can click [HERE](http://amzn.com/w/2HEUV9LMHD9HT) and it’ll take you to the wishlist that I’ve created for this specific setup.  Either works.

[TP-Link TL-R600VPN Router](http://www.amazon.com/gp/product/B007B60SCG?psc=1&redirect=true&ref_=oh_aui_detailpage_o01_s00)

[Ethernet cables x2](http://www.amazon.com/gp/product/B018RBXT1A?psc=1&redirect=true&ref_=oh_aui_detailpage_o06_s01) (any will work, this is just what I had purchased)

[Ubiquiti Bullet M2](http://www.amazon.com/dp/B002SYS22E/ref=wl_it_dp_o_pC_nS_ttl?_encoding=UTF8&colid=2HEUV9LMHD9HT&coliid=I13BZD1BM65WD7)

[8db Antenna](http://www.amazon.com/Engenius-Outdoor-High-Antenna-EAG-2408/dp/B000VIA4CA/ref=pd_sim_147_3?ie=UTF8&dpID=31jXIbforRL&dpSrc=sims&preST=_AC_UL160_SR160%2C160_&refRID=1QMS7AD3JM8X243FQMJK)

[POE adapter for M2](http://www.amazon.com/gp/product/B002R7JPGE?psc=1&redirect=true&ref_=oh_aui_detailpage_o06_s01) (Power Over Ethernet)

If you have multiple items that use POE you could get a [switch](http://www.amazon.com/Ubiquiti-TS-8-PRO-ToughSwitch-Advanced-Controllers/dp/B00CXU1NHY/ref=sr_1_2?ie=UTF8&qid=1456423025&sr=8-2&keywords=ubiquiti+toughswitch+poe) instead of the above adapter, but for me I personally only have 1 thing that needs POE so it wasn’t worth it.  Maybe in the future I might switch over to POE but for now this works.

Here’s how I have the M2 and 8db Antenna mounted on my 8020 cart.

[![IMG_3355](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3355.jpg)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3355.jpg)

The router that I use is mounted behind my monitors there (behind the sign that I “acquired” from a set on Vinyl) only because previously before I used the M2 setup I was running a wireless router as my AP (access point), which you can see below (this is right after I installed the M2, so the ASUS router was still installed).  I needed the hight for the ASUS router and I only had 2 days to prep for Odd Mom Out Season 2 so I didn’t have a chance to re-run the cables into the cart itself.  I’ll take care of that once this show is over to stream line it a bit.

[![IMG_3201](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3201.jpg)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3201.jpg)

**SETTING UP THE ROUTER**

Static is King.  You want static IPs for pretty much everything connected to the router so you always know the IP addresses offhand (You’ll end up memorizing them all at some point, it’s bound to happen).

For me I have the following set up:

192.168.0.1 – Router webUI

192.168.0.120 – BULLET M2 webUI

192.168.0.150 – BMC Smart Video Hub

192.168.0.243 – A CAM COLR (last 3 numbers are the same as the serial number on the unit)

192.168.0.251 – B CAM COLR (last 3 numbers are the same as the serial number on the unit)

**SETTING UP THE M2**

Setting up the M2 as an access point is pretty straight forward if you know what you’re doing,  I had no clue, so it was a bit frustrating at first.  What I wanted to do was be able to have the router be the hub for everything to connect to (for the M2, my mac mini, and my SmartVideoHub), let the M2 be the AP in which the COLRs communicate with, and still be able to access internet through the wifi / phone hotspot when I need to, without disabling the M2 to be able to access internet (to be able to send emails or write this post for example).

The ASUS router I used first had a default gateway of 192.168.1.1, that caused problems for me to be able to connect to the M2 and internet at the same time, so I changed the gateway to 192.168.0.1 (which is default for the TP-Link btw).  You can change this to whatever you want, I just found 192.168.0.1 to work best for me.

EDIT: When doing research online for the M2 I read that people were having a hard time changing the password.  If you click the KEY icon next to ADMINISTRATOR USER NAME (Under the SYSTEM tab) you can change the password to whatever you want.

[![Screen Shot 2016-03-18 at 5.56.13 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-5-56-13-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-5-56-13-pm.png)

Here are the settings I ended up with to get the M2 to work on my LAN (I have since changed the M2 IP to 192.168.0.120 as I stated above)

[![IMG_3270](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3270.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3270.png)

The main thing to take away from this is that you want the M2 to be setup as a BRIDGE and that you want the Gateway and Primary DNS to be the same (secondary DNS is set to Google by default).  This allows your M2 to work on the same network as the router, so that when you connect the COLRs to the M2 AP then it will still show up in LiveGrade at the specified IP address that you configured it for.  Otherwise you’d have to have the M2 plugged directly into the computer you want to use it with, this way you at least can run additional units on the same router if need be (expandability!)

One thing you absolutely HAVE to do is disable airMAX.  For some reason it just doesn’t work if you have it enabled, something to do with their proprietary devices or something like that (they even say in their own documentation to disable it!) and it’s turned on by default.

[![Screen Shot 2016-03-18 at 1.02.29 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-02-29-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-02-29-pm.png)

Under the WIRELESS tab, here is how it looks for me:

[![Screen Shot 2016-03-18 at 1.03.22 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-03-22-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-03-22-pm.png)

You have the WIRELESS MODE as Access Point, you have the SSID to whatever you want, and then down below you can set your SSID password to whatever you want.

One thing to note: You can set the Frequency MHz to AUTO if you want (it’s this way by default) or you can specify it.  This dictates what channel the COLR is set to in their UI.  In NYC there’s a LOT of WiFi interference everywhere so I tried them all out and found that 2452 (channel 9) works the best.  you can change this to whatever you want if you’d like.  If you’re having issues or congestion you can see what channels other WiFi devices are around you by going to the top right dropdown menu labeled TOOLS and selecting SITE SURVEY.

[![Screen Shot 2016-03-18 at 1.11.31 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-11-31-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-11-31-pm.png)

[![Screen Shot 2016-03-18 at 1.12.30 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-12-30-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-12-30-pm.png)

You can set your frequency to something other than what is commonly used to avoid any issues if you need to.

Once you have it all set up it should look something like this (I have the COLRs connected already on my system, and this is the STATIONS tab selected btw)

[![Screen Shot 2016-03-18 at 1.02.20 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-02-20-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-02-20-pm.png)

**SETTING UP THE COLR**

There are a few different ways you can set up the COLRs: Set them to AP mode (Access Point) and connect to the WiFi via your computer or phone (the WiFi name will be COLR and the last 4 digits of the serial number, so COLR0243 in my case), direct Ethernet connection, or USB. The nice thing is the COLR UI will tell you what the IP is on the screen with whatever your choice of connect is.  Personally I like USB as it’s always 192.168.100.1 and you can keep your settings the same if you want.  You will need a laptop or tablet that has a USB port on it FYI.

Once you connect to the COLR you’ll be greeted with this screen:

[![Screen Shot 2016-03-18 at 1.40.08 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-40-08-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-40-08-pm.png)

For the purpose of this guide I will only be dealing with the “NETWORK SETTINGS” section of the COLR, the rest will be covered in my full review.

When you select Network Settings, you see this screen.  This is how it looks for me since I have the COLRs already set up on my system.

[![Screen Shot 2016-03-18 at 1.41.52 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-41-52-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-1-41-52-pm.png)

To work with the COLR you want to select INFRASTRUCTURE and then select BROWSE next to the SSID.  A screen will pop up and you can select the SSID of your M2.  From there, select the security measure you want (WPA is what I did), enter the password and then you set your IP address.

Here’s where you want to set the COLR to STATIC and then set the IP of the address to whatever you want.  I suggest setting it to the last 3 of the serial number for ease of troubleshooting later on (such as the A camera one for me is 243 and the B camera one is 251, easy to remember which is which when looking at the IP address).

[![Screen Shot 2016-03-18 at 4.55.17 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-55-17-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-55-17-pm.png)

Once you set everything, and hit apply, it should take about 15-30 seconds for it to connect to the network and then you’ll be able to see it display on the COLR UI like so:

[![IMG_3375](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3375.jpg)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3375.jpg)

Once it’s on the network you can go into LiveGrade, click DEVICES, select ADD DEVICE to the slot you want, and then select ADD TERADEK DEVICE

[![Screen Shot 2016-03-18 at 4.32.55 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-32-55-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-32-55-pm.png)

[![Screen Shot 2016-03-18 at 4.37.54 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-37-54-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-37-54-pm.png)

And now it should show up in your device slot

[![Screen Shot 2016-03-18 at 4.37.12 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-37-12-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-37-12-pm.png)

if you hit CONFIG you will see this screen which will allow you to see the IP address, the serial number, the state of the COLR, and allow you to disconnect it as well as go to the webUI (which just launches a new window with the same IP address).

![Screen Shot 2016-03-18 at 4.37.20 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-18-at-4-37-20-pm.png)

Congratulations! Hopefully everything worked for you the first time, if not, then we move on to my not-so-favorite part….

**TROUBLESHOOTING**

The very first time I used the COLR I used an ASUS router and a 5GHz band.  It worked for the most part but had some dropouts due to the Paralinx also being on the 5GHz spectrum.  So I switched to the 2.4GHz band and didn’t have any dropouts.

Then I was having range issues with the ASUS being more than 50′ away and through walls.  So I decided to do some research on other APs and a friend who works in IT suggested the M2.

I ordered everything above (minus the TP Link), got it all set up on my cart, and everything worked great when I was at the rental house (which it always does).  I ended up just using the ASUS router as is without using the WiFi aspects of it (I actually couldn’t find a way to disable the wifi at all, would have preferred that and I suppose that caused some of my issues but I decided to just purchase the TP-Link right out as that’s what Tom had suggested, since that worked for him).

[![IMG_3204](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3204.jpg)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-img_3204.jpg)

DAY01 went off without a hitch, up until hour 10, then I started having weird disconnect issues.  The COLR would connect to the M2 but wouldn’t assign an IP address for some reason,

[![Screen Shot 2016-03-10 at 12.40.34 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-12-40-34-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-12-40-34-pm.png)

I tried kicking it off the network, but then it would connect and still have the same issue.  I did a factory reset on the COLR but it still wouldn’t assign an IP address on the device.

The only thing that worked was connecting to the COLR via USB, connecting to another network, then reconnecting to the M2.  Was super odd. I thought that kicking it off the network would have fixed it but then it still continued to happen until I could reset it manually via USB.

That worked for a while until it did it again randomly, this time BOTH cameras did it.

[![Screen Shot 2016-03-10 at 12.44.55 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-12-44-55-pm.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-12-44-55-pm.png)

I was going nuts.  I could see the cameras connected to the network but I couldn’t access it in LiveGrade

[![Screen Shot 2016-03-10 at 11.58.21 AM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-11-58-21-am.png)](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-11-58-21-am.png)

![Screen Shot 2016-03-10 at 7.52.12 PM](/assets/images/setting-up-the-teradek-colr-to-work-with-the-bullet-m2-screen-shot-2016-03-10-at-7-52-12-pm.png)

I tried everything I could think of, tried updating the firmware on the M2, replaced the antennas on the COLR itself, nothing worked.

So I ordered the TP-Link to see if it was a router issue.

Since I had already set up everything on my ASUS router to be on the 192.168.0.1 gateway the TP-Link was just plug and play since it’s default is 192.168.0.1 and I didn’t have to change anything.

The only downside to the TP-Link is it doesn’t have a way to detect static IPs on the network natively to the webUI whereas the ASUS does via it’s Network Map function (which is pretty cool).  However you can get an app called AngryIP or IP Scanner and it will do the same thing.  It’s just a stand alone app.

I switched to the TP-Link on DAY06, it’s now DAY10 and I have yet to have any dropout issues with the COLRs in the M2.  I don’t know if it’s an ASUS thing, or if it’s a issue with having the wireless enabled on the ASUS or not, but what I do know is that the TP-Link worked flawlessly out of the box, which is what I’m currently using.

For the time being I still have my IS-Minis on my cart as a backup in case things go super wrong with the COLRs but so far this week I’ve had zero issues with them, even outside in the middle of Times Square for steadicam shots.

If you’re having issues feel free to post a comment below and I’ll try my best to help or put you in touch with Teradek directly.  They’ve been a huge help in this process.

The full review is coming up soon.  Spoiler alert: I’m a big fan of these things. Especially CameraLink. But more on that later.