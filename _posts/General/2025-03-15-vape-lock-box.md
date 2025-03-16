---
layout: post
title: "Vape Lock Box"
date: 2025-03-15
permalink: /:categories/:title
categories: Project
series: General
excerpt: "Friends vaping too much? Make 'em pay!"
picture: /assets/vector/placeholder.png
---

A goofy fun project to explore some new areas like microcontrollers, servos, and stepper motor programming with a Raspberry Pi Zero and Pico with an incredibly overcomplicated mechanism and equally over complicated code running it all.

# The Problem
Everyone always comes over to our house and wants to hit anyone and everyone's vape. This obviously causes a lot of tension as those with a vape feel that they are losing precious puffs at the cost of what? A burnt coil? Everyone's gross mouth juice? It's a real problem, and a real problem deserves a real solution. This sparked a conversation, how can we solve this? Obviously we need to over engineer a super complicated means to give the people what they want, but at a cost. What is that cost you might ask? Well only some public shame and $1 on Venmo of course!

# The Idea
Here's the idea, we have a box mounted on the support pole in the center of the basement that houses the precious puffer. To access it, you gotta pay up, $1 to start, and after you pay up, you have to sit through the song and dance of shame. The lights go into casino mode, music plays, a countdown starts, and the vape presents itself from the box for a set amount of time. Drink up while you can because the sweet puff juice will retreat back to its home in 15 short seconds.

It sounds crazy, I know, but the execution of something like this started to sound like a really fun project and a really fun opportunity to mess with some stuff that I have never had a reason to use, but always wanted to. Getting to play around with servos and stepper motors and some new Raspberry Pi's was quite appealing. On top of that this was going to require quite a bit of code and some integration with my Home Assistant as well as some 3rd party APIs which is always fun to play with that. Lastly, getting to use a new tool, Onshape, for some 3D modeling in the browser which I have been wanting to give a try and see if I can transition from Fusion360.

# The Execution

## First things first, a trip to Microcenter
The first step to any good project is always a trip to Microcenter. This time I needed some new Raspberry Pi's. I spent some time researching the various micro controllers out there like the ardiuno nano but came to the conclusion I wanted to stay with Raspberry Pi since I could make use of the MicroPython implementation but quickly learned that ardiuno supports it too, oh well. I grabbed a new Pi Zero 2 and Pico 2 just for safe measure since I was not exactly sure if I was going to be able to do everything I needed with the Pico 2. I have no idea what the Python code is going to turn into and was a bit worried it could overload that board, but I do want something that is low power, so we will see in the end which one makes the most sense. Regardless, I am sure I will find another project to use whichever one I don't use on this one.

Along with that I also got some breadboards, dupoint wires, and some continous rotation servos from Amazon.

At this point I felt I had more than enough things for this project and was not really sure if I was even going to use all of this stuff, but like I said, I have always wanted to do more with servos and steppers and what not so I figured it was an *investment*.

<<<<<<insert pic of MC haul>>>>>>


## The model
For this project I am using Onshape, some friends wanted to help model and collaborate so this was the obvious choice and is something that I have wanted to try for a while since Fusion is a bit clunky, and they are putting so many things behind a paywall that it is a shell of what it once was with the hobbyist license.


