---
layout: post
title: "Multi-tasking throttling hot-fix on OSX"
date: 2017-06-27T19:47:20+00:00
categories: [DIT, Workflow]
tags: [apple, dit, film, imac, mac, mac pro, macbookpro, OSX, throttle, throttling, trashcan, workflow]
image: /assets/images/multi-tasking-throttling-hot-fix-on-osx-featured_image.jpg
---

A fellow DIT named Alex Carr figured out this fix within OSX that fixes multi-tasking issues when copying to one or more sources.  What exactly does this mean and why does it matter? I’m glad you asked.

Essentially when you try to copy from one source to another, OSX will prioritize the files in order.  When you copy from one source to multiple sources, OSX will slow that to a crawl and evenly distribute the copying power, even though it has incredible bandwidth.  Why does it do this? Who knows why, and more importantly why Apple enabled this (remember 2010 when you could copy multiple files across destinations without issue? yeah welcome back to that).

Another main reason this is important is because of rendering and copying to the same destination.  If you were creating dailies in resolve before this fix, you would have to wait until your copies finished before you could start your transcodes.  This is fine, for the first mag, but if you’re on a commercial with multiple cameras, you can’t keep up at all because OSX won’t allow it to read & write at the same time on the same source and thus your renders will crawl to a halt until your copies are done.

Now WITH this fix, you can render and transcode at the same time, as well as deal with multiple copies of .ari files if you need to.

[![]({{ site.baseurl }}/assets/images/multi-tasking-throttling-hot-fix-on-osx-screen-shot-2017-06-27-at-3-16-44-pm.png)]({{ site.baseurl }}/assets/images/multi-tasking-throttling-hot-fix-on-osx-screen-shot-2017-06-27-at-3-16-44-pm.png)

Text for easy copy & paste:

Set temporarily:

sudo sysctl -w debug.lowpri\_throttle\_enabled=0

Set permanently through reboots:

sudo sh -c ‘echo “debug.lowpri\_throttle\_enabled=0″ >> /etc/sysctl.conf’

If you want to disable this, just copy/paste the same code but with a 1 instead of a zero

BTW using SUDO will prompt you for your admin password, because it is enabling it at the root level, so if you’re not comfortable with this then that is up to you to make that decision. Obligatory decree of I’m not responsible if anything happens to  your machine, you use this at your own risk, blah blah blah…but I highly doubt anything will happen, but you have been warned! (do it anyway)

If you want to know what this effects on your machine, it essentially will effect your iCloud syncing services,  timemachine, spotlight and user experience in the UI. That’s it.

If you want to see how to do it, Alex has made this video demonstrating this:

<https://asciinema.org/a/9am696gui0jpnvh4hvduv6clw>

Full credit goes to https://github.com/tnk3r