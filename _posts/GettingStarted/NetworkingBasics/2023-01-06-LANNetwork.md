---
layout: post
title:  "What is a LAN?"
categories: GettingStarted_NetworkingBasics
permalink: /:categories/:title
excerpt: "How do devices in your home talk to the internet? How does a local network work to connect all your devices and let them talk to the internet? Read about a LAN to learn one of the fundamental concepts of networking."
---

<div style=img><img src="/assets/network.png"></div>

\
I think that having a good understanding of networking is essential to landing your first IT job and is a super important aspect as you progress your IT career. No matter what role you end up in, knowing how networking works and how computers talk to one another is key to your success and will make you stand out from the crowd. To start things off we are going to begin talking about what a LAN is.

<br/>
*Topics we are going to cover in this article may require that you read other articles in the getting started series*

<br/>

# What is a LAN Network?
LAN is an acroynm that stands for local area network and refers to a computer network composed of IP addresses that fall into what is called the `private IP address space`. You can check out our article on [What is an IP Address] to learn more about this topic. One of the easiest ways to think about a LAN network is to think of your internet network that you have at home. You probably have a router that was given to you by your Internet Service Provider that you connect all of your devices to at home. That is a LAN network!
\
<br/>

## How a LAN network is setup
Lets stick with the example of your network at home to better explain how a LAN network works and how it is setup. In your home network you will have a single router, usually provided by your ISP that you use to connect your devices to. That router is going to end up doing double duty by serving as the router for the network and your wireless access point for all the devices in your home that need to connect wirelessly.

Everything that is connected to the router and is part of our LAN can talk to one another through the router. This is how for example, a Chromecast/FireStick/AppleTV works when you connect and play content from your phone. Since the streaming device and your phone are connected to the same router and part of the same LAN, when your phone sends a request to connect to the streaming device the router takes that request and sends it to that device on your network.


<br/>
Lets looks at this example below. In this digram we have a basic rendition of a home network. In the middle we have our router (It's wireless network is named TechBytes-Home) and we have a couple of devices connected via WiFi and one single wired device. You will also see there is a single connection coming from the router marked as ISP Connection going out to the Internet. Everything that is connected to the router (excluding the ISP Connection) either directly or wirelessly is part of our LAN. When a device wants to reach a resource on the internet everything is 'routed' through the router, hence the name. The routers job is to forward that traffic out to the internet and when it receives data back it will route it back to your device. If you want to learn more about how a router takes your devices request and forwards it to the internet you should check out our article on [NAT](http://it-techbytes.com/gettingstarted_networkingbasics/What-is-NAT), one of the most important concepts that makes the internet work.

<div style=img><img src="/assets/What is a LAN.drawio.png"></div>

<br/>
You will notice each device in the diagram is assigned an IP address. This is the role of the router. Each device that connects to your network must have its own unique IP address and when a new device connects to the router it asks for an IP address. This is using a proctocol named `DHCP` that we cover in another of our [Getting Started Articles](http://it-techbytes.com/gettingstarted_intro/Getting-Started-in-IT). Notice all the devices have a simiar IP address format with only the ending number being different. Lets talk briefly about the most common LAN IP address configuration.

### Baisc LAN Networking
If you thnk about your current home network you probably have a lot more devices connected that what is shown in the diagram so your router has to assign all of them an IP address and keep track of all of those addresses it assigned. Routers are specifically designed to do this and keep what is called a routing table of all the devices connected to your network. 

You may be wondering, how does the router decide what IP addresses to use when it needs to assign a new one to a device? This is based on configuration that you can set on the router and for most they have a default configuration that is used that allows users to plug-in-play when they receive it from their ISP. For 95% of home routers they are all using the same network configuration, this configuration being standardized can be very helpful when needing to troubleshoot issues and ensures the most basic home network setup for users that don't want to go in and have to mess with things.

For your LAN there are a couple of things that determine how your network is setup. These are your `default gateway`, and `subnet`. LAN's also must use only specific IP address ranges that don't interfere with IP addresses used for networks differen than a LAN. The IP addresses used for a LAN are part of what is called RFC1918, one of many standards set for networking. You can read more about RFC1918 in our [What is an IP Address](http://it-techbytes.com/gettingstarted_intro/What-is-an-ip-address) article. For now lets use the example of the most common LAN IP address range, 192.168.1.0-192.168.1.255.

Lets break down how this IP range works. In our diagram above you can see the router is assigned the IP address 192.168.1.1. This is the first address in our range and for any network, this address is reserved for what is called the `default gateway`. So in this case our router is our networks default gateway, which means that is the device that will route all of our requests to the internet. Every address after that is available for devices that connect to the router. That means there are 253 devices you can have connected to your home network. That is a lot!

If you are keeping track of my math though you may have noticed that 253 devices doesn't make sense when our range is 192.168.1.0-192.168.1.255. There should be 254 devices right? Not exactly. The last address in any given IP range is reserved for what is called the broadcast address. Like a lot of things in this article you can read more in our [A Basic Network](http://it-techbytes.com/gettingstarted_intro/A-basic-network) to get a better understanding of now IP addresses, and subnets work to form a network.

## Lets do some exploring
Now that we have talked about how a LAN works and its setup, why don't we take a look for ourselves? Our examples included a home network which you are probably reading this article from so why don't we see how our own home network is setup! Remember how I said 95% are all setup the same, well lets find out if you are one of the 5% with something different!

Where to get started is going to depend on what kind of devices you have available at your home. I will show an example on Windows, MacOS, and iPhone but if you have something different a quick Google should get you squared away.
#### **Windows**
On any version of Windows you will start by opening the command prompt. Type in this command which will list all the networking devices your computer has. You may have to scroll to see the networking device you are currently using. For example, I am connected to a wired network but also have a configuration for wireless that is currently blank.
{% highlight cmd %}
ipconfig /all
{% endhighlight %}
<div style=img><img src="/assets/ipconfig.png"></div>

#### **MacOS**
On MacOS things are a little bit more complicated, you can get the networking information from the terminal like windows but it requires a couple of commands to get everything. The most basic information can be returned with this which is assuming you are connected to a wiresless network.
{% highlight terminal %}
ifconfig en0
{% endhighlight %}
Instead an easier way to see this information is to go to System Settings > Network > _click on the "Details" button for the network you are connected to_ > TCP/IP where you can see information like the screenshot below.
<div style=img><img src="/assets/macosip.png"></div>
