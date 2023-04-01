---
layout: post
title:  "Understanding Windows Server"
date:   2023-03-31
categories: GettingStarted_WindowsServerAdmin
permalink: /:categories/:title
picture: /assets/WSlogo.png
excerpt: "Windows Server helps businesses run critical services to support their IT infrastructure and employees."
---

Windows Server is a version of Windows specifically designed to run critical applications and services that a business needs. Windows Server is also the backbone of every organizations IT infrastructure. In order to host a Windows enterprise environment with computers and users, you must have Windows Server.

Windows Server looks and functions almost identically to the Windows operating system that runs on a laptop or desktop computer, but there are a few key differences. First, Windows Server is missing a lot of the bloat that a normal Windows install has. It is a barebones Windows operating system that has the minimum software and services to function. If you need additional features, they can be added from the Windows Server Manager that is installed.
<br/>
<div style=img><img src="/assets/winserman.png"></div>
<br/>
From here you can add roles and features to your server. Some of these include AD DS, DNS, DHCP, IIS, File Storage, Remote Desktop Services, and the list goes on. This page is the main place where you can configure any Microsoft services to run on the server. These configurations will always be the most up to date versions of these features and can be installed all on a single server but ideally you would have a separate server for each of these functions as that is best practice.

Windows Servers can also be used to run 3rd party software. It will be very common in an enterprise environment that you may need to run or host software for the business users of the company. The software vendor will provide you with an installer for your Windows Server and you may also be required to install some roles and features like IIS for example so that the app can host a web page that users can visit.


### Windows Server Versions
Windows Server, like Windows desktop has various versions however they do not follow the same naming convention. For Windows Server the convention is tied to the year that version was released. For example, these are the most common versions of Windows Server you will see in the wild:

| Windows Server 2008
| Windows Server 2012
| Windows Server 2012r2
| Windows Server 2016
| Windows Server 2019
| Windows Server 2022

The Windows Server versions are setup so that each release is supported for a long time in order to ensure that IT admins are not having to constantly uplift their servers to the latest version. Eventually though, Microsoft does pull the plug on their older Windows Server versions and will no longer release security updates or regular patches. This is a big deal right now as Windows Server 2012 is reaching its end of life in October of 2023. Admins are having to scramble to make sure they can get all of their servers uplifted to a newer version of Windows Server to ensure they are not vulnerable to security flaws, and don't have to pay a large amount of money to Microsoft for extended support if they can't upgrade in time but need security updates.
