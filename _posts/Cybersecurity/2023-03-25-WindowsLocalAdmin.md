---
layout: post
title: "Setup an Administrator Account in Windows"
date: 2023-03-25
permalink: /:categories/:title
categories: Security
series: Security
excerpt: "Improve the security of your Windows install at home and reduce the potential risk of becoming victim to a cyber-attack"
picture: /assets/Windows-def.png
---

By default, when you setup a Windows install on your personal computer, your account becomes a local administrator by default. This configuration is not very secure but does make it easier to use your computer right out of the box allowing you to install software and make any changes to your PC without needing to supply your credentials every time. This ease of use is not worth the additional security risk that this configuration creates.


## How Does Administrative Access Work in Windows?
In order to complete certain actions within Windows there can be the requirement that you have Administrative access. The most common example is when installing software, you often times need to have Administrative access so that it can write files to protected locations within the computer. Another example is if you right click on a piece of software, you have the option to "Run as administrator" which will force the software to run with those privileges.

An important part of administrative prompts on Windows is something called User Account Control (UAC). UAC was introduced in Windows Vista and is a key component to improving the security of the Windows operating system and has stuck around in every OS version since. The idea with UAC is that when a program requests Administrative access it gives the user a prompt that looks like this. 

<div style=img><img src="/assets/uacconsentprompt.png"></div>

<br/>

This prompt is designed to inform the user there is something running on their computer that is requesting Administrative rights. The program is not granted these rights unless the user clicks Yes on the prompt. This greatly reduces the risk of an automated attack occurring on the computer without the user knowing. As you can see, the prompt asks the user to select Yes or No. This is the default behavior that you have also probably observed on your computer when installing software or launching some programs. This means that the account you are currently logged in with is already an Administrator on the system so all you have to do is approve or disapprove the request. This behavior, while more secure than not having UAC at all, still has security risks as letting your regular user account be an Administrator leaves you open to attacks that can bypass this UAC prompt.


## Checking if you are an Administrator
I can guarantee if you are using a personal computer with Windows your account is an administrator already, but if you wanted to double check there are a couple of ways to tell. The easiest way is to open the Command Prompt and type in `net user <yourusername>`. This command will pull back information about your users like the last time you set your password, if it will ever expire, and what groups you are a part of.
<br/>
<div style=img><img src="/assets/netuserbrad.png"></div>
<br/>
As you can see my user is a part of the Administrators group which means I have unlimited access to make any changes to my computer without needing to do anything except accept those UAC prompts, or maybe not accept those UAC prompts...

Another way you can check this is by using a neat little shortcut to open the Local Users and Groups snap-in. This command is super helpful when working in a corporate environment where you may need to quickly check what users and groups have access to do what on a computer or server. From your start menu type in `lusrmgr.msc` and click on the option that comes up.
<br>
<div style=img><img src="/assets/lusrmgr.msc.png"></div>
<br>
Within the Local Users and Groups snap-in you can click on Groups and then double click Administrators to see the group membership. You can see my user account is a member of this group.
<br>
<div style=img><img src="/assets/lusrmgr.png"></div>
<br>

## Why is being an Administrator a security risk?

Being an administrator by default on your computer has quite a few security risks. With the introduction of UAC Microsoft made major waves in reducing the types of malware and other viruses that took advantage of the fact that users were administrators by default. Those malwares and viruses could run with those privileges without any user interaction and without the user knowing anything was happening. UAC now makes the user decide if they want to allow software to run with Administrative privileges and in theory if the user does not recognize the software requesting this access they would click No and the software would not be able to run. Most viruses and malware are looking for this Administrative access so they may disguise themselves as legitimate software so the user is more inclined to click Yes on those prompts. It can be difficult to protect against these types of attacks even with removing the regular user account from being an Admin, but there are other attack types we can eliminate by removing this Admin access by default.

The other attack types that pose the largest threat to having Administrative access by default are attacks where the malware or virus is able to disable UAC prompts. This is something you can actually do yourself if you wanted to test it out. Navigate to the Control Panel > System and Security > Security Maintenance > Change User Account Control settings. Notice trying to change these settings gives you a UAC prompt to confirm since you must be an Admin to change this. Attackers will usually rely on users blindly clicking Yes on the UAC prompt when their malware tries to change this setting. Once this setting is turned to Never Verify, no UAC prompts will come up when something is requesting Administrative access allowing the attacker to run and install any software they want.
<br>
<div style=img><img src="/assets/uacnever.png"></div>
<br>
With this set to Never Verify, try and right click on something and select Run as administrator. You will notice the program will instantly launch without prompting you for anything.

Attackers can also use methods that with UAC enabled, those prompts can be bypassed all together. That means even with UAC enabled an attacker could run software or code on your computer with Administrative privileges and you would never know. Being an Administrator by default means the attacker does not have to do anything to get those privileges, they do not need to steal a password, try and escalate to Admin, or do anything except make you try and click on a link that will run their malware. This problem can be resolved quite easily though by removing your Administrator access.


## How do we fix this problem?
Thankfully fixing this problem is quite easy. By default, Windows has a separate Administrator account that is disabled and can be used to let programs and other things have administrative rights, while your user is set as a regular user account and does not have this access anymore.

The first step is navigating to `lusrmgr.msc` again like we had earlier except this time we are going to click on Users and then double click the Administrator account. You will see that the check box for Account is disabled is checked.
<br>
<div style=img><img src="/assets/lusrmgradmin.png"></div>
<br>
Click the check box for Account is disabled to re-enable the account. Click Apply and OK. Now right click on the Administrator account and select Set Password... You will see a screen that pops up giving you a warning about changing the Administrator account password. Click on Proceed. In put a secure password in the prompt and ensure that you remember this password. It is what you will use to do anything on your PC that requires Administrative privileges!
<br>
<div style=img><img src="/assets/adminpwdwarning.png"></div>
<br>
With the Administrator account enabled and the password set now it is time to remove Administrative privileges from your regular user account that you are signed into the computer with.
Navigate to Control Panel > User Accounts > User Accounts. From here you can select Manage another account and you can see there should be two accounts listed here now, your account and the Administrator account that we just enabled. 
<br>
<div style=img><img src="/assets/changeaccounttype.png"></div>
<br>
Go back to the previous page in Control Panel and select Change Your Account Type. From this screen select Standarrd and then Change Account Type at the bottom.
<br>
<div style=img><img src="/assets/changetostandard.png"></div>
<br>
Now if you go back to Manage Another Account, you will see your account no longer has the Administrator role assigned.
<br>
<div style=img><img src="/assets/manageaccountnoadmin.png"></div>
<br>

The last thing you need to do is sign out and then back into your PC and you have successfully removed Administrative privileges from your regular user account. Congratulations you have made your Windows OS significantly more secure! When you get a UAC prompt you will now notice that instead of being prompted for Yes or No, you will instead need to type in the password you set for the Administrator account.
<br>
<div style=img><img src="/assets/nouacnoadmin.png"></div>
<br>

With this setup, even if you accidently click on malware or a virus and it tries to disable UAC you will be prompted for your credentials instead of the Yes or No. This will give you an opportunity to double check what software is trying to launch with Administrative privileges. Even if you do accidently input your Admin credentials to disable UAC, when the attacker’s software tries to gain Admin to run other software, even with UAC disabled you will still need to provide your credentials for the Administrator account. This will give you some additional security and time to realize that there may be something trying to run that you did not do yourself.
