---
layout: post
title: "Using Pomfort LiveGrade with DaVinci Resolve 9 (lite)"
date: 2012-08-09T01:50:08+00:00
categories: [DIT, Tier1, Workflow]
tags: [Alexa, CDL, CUBE, DaVinci, dit, LiveGrade, on set, pomfort, Resolve, Resolve 9]
---

I’m covering this blog entry in regards to the CDL mode on LiveGrade.  Once I get some free time to play around with the Alexa mode and fully test it out I’ll update this post with those screenshots.

You have an Alexa mode and a CDL mode where you can add in a 3D LUT with whatever you want on it (for this movie I’m using a Film Emulation LUT provided by Deluxe).  LiveGrade only takes iridas .cube files of size 32, so make sure you have that.

Make sure you set up your LiveGrade to have the 3D LUT you’re using to be loaded first (notice the filter order, this will change depending on what the post house wants, for this show they want the LUT first then the CDL ALWAYS ASK ABOUT THIS.). Then you have your Color wheels that you can balance color.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-5-00-37-pm.png "Screen Shot 2012-08-08 at 5.00.37 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-5-00-37-pm.png)

My curve looks drastically different from a REC709 3D LUT because I’m applying the Film Emulation LUT that they’re using for color on the dailies on this show, so that’s what I’m going off of with my monitoring.

To create a LUT based off the current grade/3D LUT you have loaded, hit APPLE + N, this will create a new grade.  You can then adjust levels as needed, then update the LUT by selecting the grade you want to update and the hitting APPLE + U.

Once you have the look you want, make sure you export both the .cube and CDL file by selecting the grade that you want and hitting SHIFT + APPLE + S which will save the CDL and then SHIFT + APPLE + E which will save the .cube file.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-5-06-20-pm.png "Screen Shot 2012-08-08 at 5.06.20 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-5-06-20-pm.png)

What I really like about LiveGrade is you can look at LogC image by choosing “Show original signal ” (APPLE + OPTION + O) or bypass the Color to see the difference in the 3D LUT that you’ve made (APPLE + OPTION + R).  Also you can check false color on your end without having to have the ACs do it all the time by pressing APPLE + OPTION + F.  Love that feature.

Now to load this into DaVinci I suggest making a smart folder on your sidebar to the following location on your laptop (Minus the Cinespace, just point it to the LUT folder) and copying the CUBE files into that folder.  I’ll explain how to load in CDLs later.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-06-at-12-33-32-pm.png "Screen Shot 2012-08-06 at 12.33.32 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-06-at-12-33-32-pm.png)

In the Cinespace folder you’ll end up making a new folder (Resolve9 let’s you have multiple folders for multiple projects, looooove that feature) for whatever project you’re on.  You can have Resolve 9 open and then add files to the folder but you have to make sure you select the wheel cog on the lower left part of the window to bring up the settings window and select LOOK UP TABLES and then click “Update Lists”.  That will update the list with the LUTs you’ve made in the folders.  **ALSO TO NOTE:**  Make sure your 709 LUT is in this folder structure as well.  I’ll explain this later.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-6-34-25-pm.png "Screen Shot 2012-08-08 at 6.34.25 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-6-34-25-pm.png)

Also things to note here.  Go to the top left, select PREFERENCES then go to MEDIA STORAGE and set the media folder to your root hard drive.  This will let you select any hard drives from here on out.  It should look like this:

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-04-47-pm.png "Screen Shot 2012-08-08 at 7.04.47 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-04-47-pm.png)

To load media into DaVinci make a new user (I do one per project) and create a new project (I do one per day). You’ll see 5 tabs at the Bottom, MEDIA, CONFORM, COLOR, GALLERY, DELIVERY.  It defaults to the MEDIA tab, then find your media by browsing to VOLUMES then your hard drive and then through folders, etc, until you find your folder with you media.  Then right click the folder, select ADD FOLDER AND SUBFOLDERS INTO MEDIA POOL and voila!

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-6-29-36-pm.png "Screen Shot 2012-08-08 at 6.29.36 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-6-29-36-pm.png)

Go to the Color tab and you should see all of your footage there.  If it’s not there, go to the CONFORM tab and go to the top left and hit the + button under TIMELINES to create a master timeline.  You don’t have to name it, just hit enter.

Now select your footage, go to the tree on the right, right click, select your 709 LUT (I made one from ARRI’s website, but you can use this with any LUT).

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-13-31-pm.png "Screen Shot 2012-08-08 at 7.13.31 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-13-31-pm.png)

This is your 709 LUT applied.  Now we’re going to check the .cube file you made. Go to Color > Memories > Save Memory A (option + 1).

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-19-02-pm.png "Screen Shot 2012-08-08 at 7.19.02 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-19-02-pm.png)

Right click the node you made with the 709 LUT, find the LUT you made, select it, and BAM there you go! You now have your 709 LUT with your CDL applied to it.  Go to Color > Memories >  Save Memory B (Option + 2).

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-16-39-pm.png "Screen Shot 2012-08-08 at 7.16.39 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-16-39-pm.png)

You can switch between the 709 LUT and your colored LUT by pressing APPLE + 1 and APPLE + 2 (I recommend having your spaces disabled from switching between spaces with use of the apple key for this reason).

Now for importing CDLs.

There’s 2 different ways to get CDLs to view properly with the 709 LUT, I’ll go over the long way first.

To import CDLs you have to go to the GALLERY tab first.  Select the Powergrade tab in the middle of the window under “Project Stills” and right click, select IMPORT and then navigate to your CDL directory.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-37-30-pm.png "Screen Shot 2012-08-08 at 7.37.30 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-37-30-pm.png)

Choose the CDL option from the drop down menu, select the CDL you want, hit enter.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-37-09-pm.png "Screen Shot 2012-08-08 at 7.37.09 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-37-09-pm.png)

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-39-06-pm.png "Screen Shot 2012-08-08 at 7.39.06 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-39-06-pm.png)

Also to note you can do this from the COLOR tab by pressing the icon in the middle of the screen, right above the timeline (in the gallery sub window, looks like a still image icon) to bring up the different stills folders.  Then you could select powergrade and import that way as well.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-41-02-pm.png "Screen Shot 2012-08-08 at 7.41.02 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-41-02-pm.png)

You should have your CDL in.  Looks like this:

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-40-22-pm.png "Screen Shot 2012-08-08 at 7.40.22 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-40-22-pm.png)

Select your footage in the time line that lines up with the CDL (in this case it’s scene 104, also your footage should be at a base node memory, if it’s not go to Color > Base Memory) right click the powergrade, select APPEND NODE GRAPH

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-48-21-pm.png "Screen Shot 2012-08-08 at 7.48.21 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-48-21-pm.png)

What this does is it creates the CDL as another node so you don’t have to add a node then put the 709 LUT in front of that one and rearrange them.  Much easier this way.  Then select the first node, right click and apply your 709 LUT.  Now you should see your CDL in the right side, and your 709 in the left side.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-54-24-pm.png "Screen Shot 2012-08-08 at 7.54.24 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-54-24-pm.png)

I like this as I like to see what the 709 shows and be able to turn off the CDL whenever I feel like it.

That’s one way, here’s the other:

Go to base memory (Color > Base Memory).  Now click on the wheel cog icon (lower left hand corner) to bring up the settings window.

Go to the LOOK UP TABLE section, then go to the 3D INPUT LOOKUP TABLE.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-35-08-pm.png "Screen Shot 2012-08-08 at 7.35.08 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-35-08-pm.png)

Select your 709 LUT and now every node will have a 709 LUT pre-applied to it.  Useful if you’re going to apply a 709 LUT to every shot and don’t want to look at LogC ever (useful if you’re just rendering from LogC to 709 via DaVinci, What I normally do for most commercials).

The reason you do Input LUT is it applies the 709 LUT first then the CDL, as opposed to the other way around.

Then go to the COLOR tab, select the clip, right click on the powergrade that corresponds, select ADD CORRECTION and voila! there you go.

[![](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-46-39-pm.png "Screen Shot 2012-08-08 at 7.46.39 PM")](/assets/images/using-pomfort-livegrade-with-davinci-resolve-9-lite-screen-shot-2012-08-08-at-7-46-39-pm.png)

Hope this helps.