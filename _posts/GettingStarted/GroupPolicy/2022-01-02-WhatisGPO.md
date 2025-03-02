---
layout: post
title:  "What is Group Policy"
date:   2023-01-01 22:10:56 -0600
categories: GettingStarted_GroupPolicy
permalink: /:categories/:title
excerpt: "Group policy is the backbone of a corporate Windows computer deployment. It allows admins to control every aspect of the Windows devices they deploy to end users."
picture: "/assets/groupolicy.png"
---

<div style=img><img src="/assets/grouppolicy.png"></div>
*This is the local group policy editor that you can access right now on your computer if you are running Windows. Open your start menu and search for Edit group policy and you should see it come up. Even though you are not joined to a domain, you can still use Group Policy locally on your computer to control certain settings and configurations if you wanted to.*

<br>

Group policy is what it sounds like, it is a set of policies that can control a group of computers. Group Policy in an enterprise environment will certainly be applied to every Windows based computer and server so that settings can be carefully controlled to ensure security and a uniform experience for all users. The main function of Group Policy is that it allows admins to set specific configurations based on the device type, the person using it, the location it is being used in, and really any combination of those and more. Group Policies can be applied to any device for any reason and there are thousands of configurations that can be set to control basic Windows functions and additional policy templates can even be downloaded to control settings in Google Chrome for example and other applications that have Group Policy templates.

One other important thing to note is that Group Policy is often referred to as `GPO` when talking with others in IT. This abbreviation stands for Group Policy Object which denotes one single specific configuration within Group Policy, but most people will understand what you mean if you say GPO when talking about Group Policy as a whole.


## What can you do with Group Policy
Let’s say for example you have 100 users at a company that are all using Windows computers. At this company you have multiple file shares that all users will need to access but to map them to each user’s computer would take forever and some users may mess it up if you give them instructions. Instead of having to set this up on every computer before you give it to a user, you can use GPO and set a policy that configures all the drive shares for all 100 computers for you. Once that GPO applies to the computer the user will see the file shares!

Another example is maybe you want to ensure for those 100 users that the Windows firewall is turned on and blocking any incoming connections. You probably also want to make sure that Windows Defender is turned on and that users cannot disable it. While you are at it you should probably remove any unnecessary user account from being administrators on those computers to strengthen the security. All of this can be configured as a GPO and applied to all 100 computers in your company, and you only had to configure it once!

This is the beauty and power of Group Policy as it saves admins hundreds of hours of time by allowing them to make configuration changes on the fly and set default behavior that will apply to all users without needing to make sure each device is configured just right before giving it to them.


## How Does Group Policy Work?
Group Policy is a feature installed when you setup Active Directory Domain Services as it is seen as a core functionality of setting up and having a domain. You can read this article that talks more about [Active Directory](https://it-techbytes.com/gettingstarted_activedirectory/WhatIsAD) and this article that talks about [Domains](https://it-techbytes.com/gettingstarted_domaincomputers/WhatisDomainJoined). Group Policy can be configured via the Group Policy Management Console directly on a Domain Controller or you can configure via the Group Policy Management Tools that are included as part of the Remote Server Administration Tools pack.

When a computer is joined to a domain it is automatically available to accept Group Policies as part of being on the domain. When you configure Group Policies those get published to your domain controller and then synced down to each device within scope of the Group Policy. When you create a Group Policy you can specify whether the configurations you are creating apply to Computers or Users and then you can scope those configurations to a specific Organization Unit or security group of users or computers. There are some best practices with this setup and process that we will cover in another article.

Syncing group policy to computer devices is something that happens on a predefined interval. In most cases the default for this sync is every 90 minutes, but that be changed. It can also be configured and is most common that GPO is reevaluated and applied upon every user logon to a Windows computer. This ensures that when the user signs in that device is getting the most up to date GPO settings configured for the domain. 

## Troubleshooting GPO Issues

As someone helping troubleshoot a potential Group Policy related issue you can also force this sync to happen. On any domain joined computer you can open a command prompt window and type `gpupdate /force` which will force the User policy to sync immediately. If you open the command prompt as an Administrator and run that command, you will sync the Computer and User policies which is usually required to ensure that all updated policies are applying.


<div style=img><img src="/assets/gpupdate.png"></div>

<br>
Group Policy objects are stored at this location in Windows. In extreme cases where things are really messed up on a device, or GPO is failing to apply you can go here and delete the Registry.pol files within Machine and User respectively. 
`C:\windows\system32\grouppolicy`
