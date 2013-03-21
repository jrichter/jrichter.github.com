---
layout: post
title: gnome 3.2 - arch linux login problem
published: true
date: 2011-09-30 20:42:41 -0500
---

I recently upgraded my gnome 3 install to gnome 3.2. Pacman threw an error so I forced the
upgrade. I am never forcing an upgrade again. :) The upgrade completed and when I rebooted
I was greeted with a sad face saying I should contact my system administrator. I hate it
when software tells me to contact me. After a brief google search I was left with people
complaining about 3.2 being unstable and what not. Thats what happens when you install
something the day its released. I decided to go on to sleep, it was almost midnight and I
had work the next day. When I got home I gave it another try, this time on the arch
forums. Much better info. I issued these commands:


    pacman -Rdd python2-gobject pygobject-devel cogl

Then:

    pacman -S pygobject-devel cogl

Once I rebooted everything worked just fine. I probably could have just removed
python2-gobject and had it work. Hope that helps someone else.
