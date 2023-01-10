---
layout: post
title:  "What is DNS"
date:   2023-01-01 22:10:56 -0600
categories: GettingStarted_DNS
permalink: /:categories/:title
excerpt: "DNS is the phone book of the internet, it helps us remember how to get to computer resources and is usually the cause of a lot of networking issues. Be warned."
---

DNS helps make our lives easier when interacting with the internet. When you meet someone and get their phone number, what is the first thing that you do? You go to your phone and add a contact for them because it is a lot easier to remember John - From Work then it is to try and remember what their phone number is. This is essentially what DNS deos for the internet! Lets learn what it is, how it works, and how troublesome it can be.

# What is DNS?
DNS is an acronymn that stands for `domain name system`. DNS is the phonebook of the internet and allows us to associate a `domain name` to an `IP address`. This is super important when it comes to browsing the internet as there are tons of IP addresses for each different resource that we access everyday. Remembering all of those IP addresses would be impossible, espically given that they can change! DNS lets us type in Google.com in the URL bar and it will figure out the rest. Lets explore how DNS works.

## Types of DNS Records
One thing to cover first before we get into how DNS works is understanding the different types of DNS records. In order to accomidate for various needs and use cases of DNS there are what are called record types that help us accomplish those needs.

| **TYPE** | **Description** |
| A Record | An A record is the most basic type of DNS record and one of the most common. The purpose of an A record is to serve the most basic DNS fucntion. Map a domain name to an IP address. mydomain.com <--> 136.76.52.244.
| AAAA Record | This is the same as an A record but instead of IPv4, it maps IPv6 to a domain name.
| TXT Record | Allows an admin to put text into a record that gets posted to the DNS server. This is most commonly used when needing to setup a 3rd party service that uses your domain. The 3rd party service will require you input a specific text record to your DNS so that they can look it up and verify that you are the owner of that domain. TXT records are also used for some functions of email.
| MX Record | An MX record is used for routing email to a domain. It is setup like a CNAME record and routes email sent to addresses @ your domain to a domain name associated to a mail server that can handle the request.
| CNAME Record| A CNAME record maps a domain name to another domain name. Ultimately the CNAME record will reach a DNS A Record where an IP address is provided to the device and it can receive the content it requested. A CNAME can be mapped to multiple CNAME records in a row, but is not recommended. blog.mydomain.com <--> mydomain.com
| SVR Record | Also known as a service record, these are used to map a domain name to a specific IP address and port number for a serivce. Some services like VIoP require a SRV record be setup. These records include a priority and weight setting to help balance loads between different records associated to the same domain name.
| NS Record| 