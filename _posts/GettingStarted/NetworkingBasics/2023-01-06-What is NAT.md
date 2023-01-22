---
layout: post
title:  "What is NAT?"
categories: GettingStarted_NetworkingBasics
permalink: /:categories/:title
picture: "/assets/WhatisNAT.drawio.png"
excerpt: "More than likely your devices do have the same IP addresses as devices connected to your neighbors home network, and really everybody's home networks. How does this work then?"
---
At the beginning of the internet all computer networking was based around IPv4 addresses where there are 4 billion different addresses that can exist which was more than enough at the time. As more and more devices joined the internet, it became clear that a solution was needed to address (no pun intended) this issue. To offer a frame of reference according to statista.com in 2020 there were 9.7 billion devices connected to the internet and predictions estimate by 2030 that number is going to triple to more than 29 billion.

If you read our [What is an IP Address](http://it-techbytes.com/gettingstarted_intro/What-is-an-ip-address) article then you know there is a finite number of IP addresses available for each computer device to use so how do all of these devices in your home talk to the internet without having the same IP address as a device your neighbor does? More than likely your devices DO have the same IP addresses as devices connected to your neighbors home network, and really everybody's home networks. How does this work then? How do these devices talk to the internet and not interrupt each other? That is where `NAT` comes in.


# What is NAT?
NAT stands for Network Address Translation and is a concept that I did not understand for a long time when I first started learning about computers and networking. Once you understand the concept it seems obvious but isn't something that is common knowledge when it comes to using the internet as for the most part it operates completely in the background. I would consider it one of the most important features of networking that has allowed the internet to grow to what it is today.
<br/>

## How does NAT work?

NAT is handled by the router. It translates your devices local IP address into something that can be broadcasted out to the external internet. Remember the problem with the limited IP addresses? Well just because there are only so many IP addresses available, doesn't mean that any person should be limited to the number of devices that they can have that can talk to the internet. If everyone's personal devices were directly on the internet there would certainly be some problems. With NAT you can have as many devices in your local network as you want, well as many as your router will support! The routers job is to take all of those internal IP addresses and translate them to one signle external IP address that will then go out to whatever internet resource you have requested.

Lets look at this diagram of our TechBytes-Home network. Lets say that the computer with the IP address of 192.168.1.2 wants to go to Google.com. For that to happen the computer requests the Google.com page. The request is sent to the router and the router knows exactly what to do. It takes that request and forwards it on to the internet via the ISP connection. When the router forwards that request on it does not use the IP address that the computer has (192.168.1.2). It actually uses an IP address that was assigned by the ISP to the router known as your `External IP address` (136.76.52.244). How does it do that? Well it uses NAT! It translates the request from the internal IP address(192.168.1.2) to the external IP address (136.76.52.244) it has and sends it on to the internet. Remember how we said whenever a device connects to your router it must have an IP address? Well it is the same for the router. When the router connects to the ISP's network, it must receive an IP address from the ISP and that is how you are able to talk out to the internet.

<div style=img><img src="/assets/WhatisNAT.drawio.png"></div>

### Why does NAT matter?
You might still be wondering why NAT is important, and why did I say it was one of the most important features in networking? With NAT you are able to significantly reduce the number of IP addresses that are needed for the internet to work. Think about your network at home, you may have 2, or 5, or maybe even 20 devices connected that all need their own IP address, if all those devices and your neighbors devices and your other neighbors devices were all directly on the internet you can see how we quickly end up at that 9.7 billion number which is significantly more than the 4 billion that IPv4 can support. Instead with NAT your 20 devices, to the internet, only look like one device with one IP address (your external IP address). That is because your router at home is using NAT to take requests for your devices and translate the IP address to one single external IP address that can be used on the internet.