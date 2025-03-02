---
layout: post
title:  "Domain Joined Computers"
date:   2023-01-01 22:10:56 -0600
categories: GettingStarted_DomainComputers
permalink: /:categories/:title
excerpt: "How do companies manage the thousands of devices for all of their employees and ensure they are all configured with the same settings? They use a Windows Domain."
picture: 
---

Joining a computer to a Windows domain allows for administrators to control all of the functions and settings of that device from one central location. It ensures that only users who are supposed to can login to the device and if they for example, leave the company, access to the computer can be revoked by disabling their domain user account. 

Most companies will automatically join all computers to their domain before they are sent out to users and will also set up a user account in the domain for that person. The user can sign into the computer with their newly created domain user account and will have permissions that are assigned to them as part of the user account creation process. Joining a computer to a domain also means that it can be managed by Group Policy which is another Windows Server role that is used to manage all of the settings for devices on the domain. 

# Domain Join Types
With the introduction Azure, Microsoft's cloud platform, administrators have the option to make their devices joined to their on premises AD or their Azure Active Directory or both. Lets cover the different types and what that means.

## On Premises Only Joined
This is the traditional method to join devices to a domain. You have an on premises domain controller that runs Active Directory and houses all of the information for your domain. Devices must be on your corporate network to access the domain and authenticate. Without a VPN connection into your network they aren't really able to do anything with the device. Also to utilize single sign-on for applications you must make use of a service named `ADFS` which is slowly being phased out by Microsoft. This join method is really not used for most companies anymore. 

## Hybrid Azure AD Joined
This method is the most common for all modern enterprises. Devices still get joined to the domain in the same way, but instead of being tied down to on premises only resources, devices now have the ability to talk to your companies Azure Active Directory to authenticate and access resources via single sign-on without needing to be directly connected to your network. The Hybrid join requires that your company have the Azure AD connector service setup and it will sync all of the computers, users, and groups from your on premises AD to the cloud so that devices can more easily be managed even outside of your network. With hybrid joined devices you also have the ability to utilize Intune, a Microsoft cloud product aimed at eliminating Group Policy and allows you to manage device settings no matter where the device is located.

## Azure AD Only Joined
In some smaller or newer companies they make use of Azure AD only joined devices. This eliminates the need for all of the on premise hardware and software to run a domain and instead all of that is setup and ran in the cloud by Microsoft. Administrators are still responsible for configuring all of these services, but there is significantly less overhead for maintaining those services. In these cases administrators have to make use of all of the cloud services that Microsoft offers for managing the devices and if there is any on premises resources that need to be accessed they cannot be integrated with the domain to get permissions and other access delegated that way. 