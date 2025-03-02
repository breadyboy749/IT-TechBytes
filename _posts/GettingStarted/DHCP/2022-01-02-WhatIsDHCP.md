---
layout: post
title:  "What is DHCP"
date:   2023-01-01 22:10:56 -0600
categories: GettingStarted_DHCP
permalink: /:categories/:title
excerpt: "DHCP is responsible for assigning IP addresses to computers on a network. Without DHCP it would be extremely hard to do any networking at the scale required in todays technology focused world."

---

DHCP is a networking protocol that stands for `Dynamic Host Configuration Protocol` and is what is in charge of assigning IP addresses to devices when they are added to a network. DHCP helps a new device obtain information for the network so that it is able to successfully connect to the router and access the internet. Without DHCP you would have to spend a lot of time manually inputting your network settings into each device that you wanted to add to the network, and then also make sure each device you setup had a different IP address so there are no conflicts. This can be very tricky to keep track of for a home network with maybe 10-20 devices, now imagine a corporate network with thousands! It would be impossible to keep track of all that information without some overlaps and would take a lot of time to get just right. That is why we have DHCP!


# What does DHCP do?
When a device connects to your network for the first time it has no idea how to configure itself within the network so that it can talk to devices and talk to the internet. There are settings it needs to receive like the `default gateway`, `subnet mask`, and `NTP server` if there is one from the DHCP server. By default almost all consumer electronics are configured to utilize DHCP by default when connecting to a network so there isn't anything you need to do for them to work, but lets understand what is happening in the background to get your device the right connection information.

<br>

With your device connecting to the network and using DHCP by default it will first send out a broadcast message on that network looking for a response from the DHCP server to get the required information. The DHCP server is always looking for these types of requests and once it picks one up, it will take it and process information for the device. It will record the devices `MAC address` and some other information so that it can create a DHCP lease for that device. Within the DHCP lease it will save a mapping of MAC address of the device and IP address it is going to assign to it. Once that lease is created in the DHCP server it will respond back to the device with all the required information for it to connect to the network. The DHCP server also assigns an expiration to each lease and relays that information to the device connecting. Once the lease expires, the device will be required to check back in with the DHCP server to get a new lease with the most up to date network information. This can be helpful if you need to make changes to your network and want to make sure all devices receive them. It can also help if you have made a bad change to your network configuration as you can catch it before devices connected check in for a new lease and get that badly configured information sent to them.

<br>

If you read our [What is a LAN](https://it-techbytes.com/gettingstarted_networkingbasics/LANNetwork) article you will know how we talked about your home network and the router that is associated with it. In this article we have been talking about this DHCP server that must exist on a network so devices can connect, but on your home network where is that server? That server is actually your home router! Your home router not only asks as a router and wireless router but it is also the DHCP server for your network and is in charge of keeping track of all of that information and giving it to your connected devices. Talk about overworked, that is often times why you can resolve network issues by restarting your router, that is because it is doing the job of what is normally three individual network appliances. The reason your router is tasked with all of these duties is because realistically for most home networks you do not need super powerful versions of any of this networking equipment, but these are complicated systems all needing to run together with one another and that can lead to potential problems. That's why a quick restart can go a long way in helping fix basic network problems at home.
