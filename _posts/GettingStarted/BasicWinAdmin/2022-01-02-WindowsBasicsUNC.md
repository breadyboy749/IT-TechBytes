---
layout: post
title:  "Windows Basics: UNC"
date:   2023-01-01 22:10:56 -0600
categories: GettingStarted_BasicWindowsAdministration
permalink: /:categories/:title
excerpt: "On a Windows computer and need to share files with another Windows computer on the same network quickly and easily? UNC will become your best friend"
---


# What is UNC
UNC stands for `Universal Naming Convention` and is a function that Windows devices make use of to connect to network resources and one another when they are part of the same network. UNC itself is somewhat generic and is only able to be used on Windows based devices and some printer resources. You can use UNC to talk to a servers shared file system or another file sharing resource and I would say that is it's most useful function.

## How do you use UNC
Using UNC is super easy. Its usage may vary depending how your network or company is setup, but for the most part you should be able to make use of it in some fashion even if that is just accessing a public file share. 
The first part involves some terminology that is somewhat widely used in the IT world, the fabled `wack wack`. What does this stand for you may ask? This, \\. `Wack wack` is a term you can use to denote the double blackslash required to start the UNC naming convention when connecting to a resource. After the \\ you will input the name or IP address of the device you would like to connect to. For example if the file share on your network is named MyCompanyFileShare and you want to connect to it, you would open File Explorer and in the navigation bar type \\MyCompanyFileShare\ to get to the root directory of that share.

<div style=img><img src="/assets/mycompanyfileshare.png"></div>

<br>
<br>
If you are needing to connect to another computer or server on your network you will use the same syntax, but if needing to connect to the root of a specific drive on that computer you will need to ensure your connection string looks like this \\Computer\C$. It is super important that you include the $ after the drive letter of the drive you would like to connect to otherwise it will not work.

<div style=img><img src="/assets/computerunc.png"></div>

<br>

## Why would you need to use UNC
Lets talk about some examples of when you would need to use UNC. If you are working in an enterprise envrionment UNC will be an invaluable tool in your toolbelt when troubleshooting issues or working on Windows servers. Here are a couple of real world examples where I have had to use UNC:


##### Example 1: 
You are troubleshooting an issue for a remote user and there is a log file, screenshot, or other configuration data you need to capture from their device but you don't want to or don't have the ability to remote in with them to gather that data and transfer to your machine. If you have local admin access on that device with your privileged account you can navigate to their files on their device without need to interact with them. From your device you will navigate to \\remotecomputer\C$ and if you are not logged in with your privileged account it will prompt you for credentials that can access those files. Input your credentials and now you can connect to that computers files to transfer any logs or other information you need without need to disturb the end user.

##### Example 2: 
You need to transfer a file from your local workstation to a server, but access is blocked because those devices are not on the same network and RDP file transfer is being blocked. You can still use UNC but just a little bit differently. This will depend on how your environment is setup, but in most cases you should be able to find a public file share that both devices can access. You can use this file share as a proxy to transfer your files to from your local workstation and then access via the server and copy them there. This type of situation is very common in most enterprise envrionments and this is a quick way to get around these restrictions. In this example on your local workstation you would go to \\sharedpublicfiles\temp\ and copy all your files. On the server you would navigate to the same location and can copy the files down to the server.

##### Example 3: 
There is a group of servers that you need to remote into to compelete some work on an application. You are remoted into each server indivdually via your local workstation and need to transfer a large .zip file full of all the configurations and applications you are installing to each server. On the first server you have taken this .zip and transferred it from your local workstation using the file transfer that is built into RDP but it took super long because you are over VPN and having to access a server network. That finishes, but now you need that same .zip file on 5 other servers to do the same work. Rather than copy from your local workstation via RDP, why don't you just copy from the first server to all of the others? As long as these servers are on the same network you can do that with UNC! From your second server open up the File Manager and type in \\server1\C$ (or where ever you have the .zip file saved) and if you have local admin privileges on all of the servers you can now access the C: drive of the first server from the second and can directly transfer that .zip file over the server network which is going to be almost instant depending on the file size and where each server is located in your datacenter.


## Lets do some exploring
On your own home network you can use UNC if you have more than one Windows device conncected to it. First you will need to determine the hostname of the computer you would like to connect to. To do so on that computer login and open the command prompt. From the prompt screen type `hostname` and press enter, remember or write down this hostname.

<div style=img><img src="/assets/hostname.png"></div>
<br>

On your main computer open the File Explorer and type in \\hostname\c$ for the computer which you would like to connect to. At this point it will probably prompt you for credentials. Type in the credentials for the user account on that computer and once connected you will now have access to the file system to copy and modify any files you need to all remotely.

<div style=img><img src="/assets/hostnamepcconnect.png"></div>
<br>

<div style=img><img src="/assets/unccreds.png"></div>
<br>

<div style=img><img src="/assets/uncconnection.png"></div>
<br>

Note that in a corporate envrionment there will probably be some more restrictions on who can connect to other users computers file shares for security purposes. If you are someone on the service desk that has a privileged account that is a local administrator on client devices then you would be able to use those credentials when prompted after you try to connect to a computers file share remotely. Same thing applies for server access, if you have an account that is local admin on the server you are wanting to connect to via UNC you are good to go, otherwise you will not be able to connect. 


