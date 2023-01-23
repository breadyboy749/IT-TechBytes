---
layout: post
title:  "What is a firewall?"
date:  2023-01-22 22:10:56 -0600
categories: GettingStarted_Firewalls
permalink: /:categories/:title
excerpt: "Firewalls, while not as destructive as they sound, are an important part of keeping a network secure and ensuring only allowed traffic can get through."
picture: "/assets/firewall.png"
---

 <div style=img><img src="/assets/firewall.png"></div>

<br>

A Firewall is a network appliance that will usually sit at the perimeter of your network and is used to filter through all of the traffic that is coming in and going out of your network. It is designed to read the information flowing to and from the internet and block or allow things based on rules set by the administrator.

In most networks the main purpose of a firewall is to block incoming traffic from the internet into the network. You may have servers running or just regular computers on the network that could be accessed if it weren't for the firewall. By default most firewalls are configured to block all incoming connections from the internet and allow everything out of the firewall if it is within your network. This ensures a firewall can quickly be stood up without needing to do much configuration if any. There are a couple of problems with this approach. What if you have something on your network and you want to allow an incoming connection to it? By default that is blocked. Also what about all those devices inside the network? They can reach out to anything on the internet by default and that may not be the most secure setup for your network. Lets talk about firewall rules, how it works to filter the traffic, and the future state of firewalls.

# Types of Firewalls
As with most technologies there are a couple of different options when it comes to firewalls. As technology has progressed along with attacking techniques so have firewalls to become powerful security devices aimed at fully protecting the traffic flowing to and from your network.

### Packet Filtering
The most basic of firewalls, this type looks at specific information in a packet and evaluates it against its rules table to see if there is a match. Depending on the match the decision will be carried out for that packet. 

### Stateful
A stateful firewall has the ability to look at an entire packet to determine if it should be forwarded on or not. This type of firewall is able to look at a TCP conversation to determine the "state" of it and whether or not it is valid or may contain malicious packets that should not be part of that conversation or have been altered.

### Application Gateway/Proxy Firewall
Application gateway firewalls, also known as proxy firewalls, are firewalls specifically designed to look at the conversations that are happening between applications and other internet connected devices. These firewalls will intercept application traffic, inspect it in more depth than a regular firewall, and make a descision based on that information.

### Next Gen Firewall
Next Gen firewalls are exactly as they are named, the next generation of firewall. With increasing attacks and complexity of techniques used by attackers, traditional firewalls are not enough to catch these attacks. A next gen firewall incorporates other firewall types along with additional advanced features to protect a network. They generally will do packet filtering, stateful inspection, deep packet inspection, along with having IDS/IPS capabilities on top of that. This is where the industry is moving as a whole as these firewalls can replace what was normally multiple different network appliances that were used to accomplish the same tasks.