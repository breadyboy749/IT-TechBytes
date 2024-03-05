---
layout: post
title:  "DIY Volume Mixer (Deej)"
date:   2024-03-04
permalink: /:categories/:title
picture: /assets/volume_nometa.jpg
excerpt: "Super fun DIY project that will test your soldering skills and provide you something you didn't know you needed"
---

# The Problem

A volume mixer for Windows is something you didn't know you needed until you have it, then you can't go back. Let me explain. Managing multiple audio streams on Windows 11 is... challenging to say the least. Depending on what you are doing, adjusting the volume for various programs in Windows 11 has some friction. You have to navigate down to the task bar and then right-click on the audio icon and open the volume mixer. This will open a full screen app that will take over whatever you are doing or looking at and if you don't click just right you will end up with the context menu for networking without realizing why because it is visualized as one big button for some reason.
<br>
<br>
<div style=img><img src="/assets/volumeicon_win11.png"></div>
<br>
When you do get the volume mixer open you can see that it is using the Windows 10 settings? Windows 11 settings? Modern UI? Not sure what Microsoft is calling this now, but it is still not the best. This menu does do the job, but again it is a huge full screen app and there are duplicates of apps on here that have multiple audio streams so it can be confusing at a glance which one you need to update.
<br>
<br>
<div style=img><img src="/assets/win11_volumemixer.png"></div>

<br>

# The Fix
This is where a volume mixer comes in, specifically the open source Deej volume mixer. <br>
[Deej Github](https://github.com/omriharel/deej)

To quote directly from their repo "deej is an open-source hardware volume mixer for Windows and Linux PCs. It lets you use real-life sliders (like a DJ!) to seamlessly control the volumes of different apps (such as your music player, the game you're playing and your voice chat session) without having to stop what you're doing."

The magic with Deej is that you can build a volume mixer yourself for very cheap, about $20-$30 depending on your taste and existing tools you may have! Creating a volume mixer that is compatable with the Deej software is super easy