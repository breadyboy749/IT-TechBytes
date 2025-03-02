---
layout: post
title:  "PAW Deployment Architecture and Planning Considerations"
date:   2023-06-04
categories: PAW
permalink: /:categories/:title
picture: /assets/secure-workstation-deployment-flow.png
excerpt: "Deploying PAW can be a real challenge there are lots of things to consider and risks that must be weighed to determine a solution that works well for your company."
---

## What is a PAW?
PAW is an acronym that stands for privileged access workstation. This question can have a couple of different answers depending who you ask and what philosophy you decide to follow. In general most people will agree that a PAW is a workstation dedicated for using privileged credentials and has some amount of separation from a users normal day to day workstation. These workstations should be hardened and only used for privileged tasks with a privileged account.

## Why PAW?
There are a lot of reasons to implement PAW. The biggest being avoidance of a phishing attack compromising a users workstation who has privileged credentials. If that user is using the privileged account on that same workstation it is trivial with modern hacking tool sets to extract those credentials for use in your domain. We will cover in more depth in a dedicated article why PAW is so important and explain these attacks.


# PAW Planning
Here are some lessons learned and general discussion from my deployment of PAW. Hopefully this can help alleviate some headache for others that embark on this journey.


## Hardware
There are multiple trains of thoughts when it comes to PAW, each with their own pros and cons. At the end of the day it comes down to cost, complexity, and security benefit. It sounds easy when you put it that way, but in reality this is the most difficult decision that has to be made and will define the deployment down the road as well.

#### Dedicated Hardware
If you were to speak to Microsoft about how they recommend PAW be deployed they are going to tell you to get dedicated hardware for PAWs. Conveniently they will suggest you get Surface devices, interesting... Technically while the most secure, this approach has the most complexity, cost, and burden for your admins. The dedicated hardware approach means that users have a regular workstation and a PAW that they need to carry around. These devices are completely separate and are only to be used for their respective purposes. The PAW machine is hardened in a way that is much more secure than the normal day to day workstations and any privileged users now have to switch devices each time they need to use a different account. I would say this approach is only applicable in cases where an extremely high level of security is required for admins. This approach also works best if the environment has been properly managed to support the usage of privileged accounts, more on this later.

For me this approach was not feasible, with admins all over the world and increased hardware costs due to COVID it wouldn't have worked. There is also additional operational overhead required to now manage these separate devices and a program and policy needs to be in place if these devices are lost or stolen and if it should be handled any differently than a normal workstation.

Here is some documentation from Microsoft on this, they are careful not to explicitly call out dedicated hardware here, but it is implied when you start looking at their policies and other items that would only be feasible if you had separate dedicated hardware for your implementation.
