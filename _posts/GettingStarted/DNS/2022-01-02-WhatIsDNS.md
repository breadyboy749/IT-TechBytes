---
layout: post
title:  "What is DNS?"
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
| A Record | An A record is the most basic type of DNS record and one of the most common. The purpose of an A record is to serve the most basic DNS fucntion. Map an IP address to a domain name. 136.76.52.244 <--> mydomain.com.
| AAAA Record | This is the same as an A record but instead of IPv4, it maps IPv6 to a domain name.
| TXT Record | Allows an admin to put text into a record that gets posted to the DNS server. This is most commonly used when needing to setup a 3rd party service that uses your domain. The 3rd party service will require you input a specific text record to your DNS so that they can look it up and verify that you are the owner of that domain. TXT records are also used for some functions of email.
| MX Record | An MX record is used for routing email to a domain. It is setup like a CNAME record and routes email sent to addresses @ your domain to a domain name associated to a mail server that can handle the request.
| CNAME Record| A CNAME record maps a domain name to another domain name. Ultimately the CNAME record will reach a DNS A Record where an IP address is provided to the device and it can receive the content it requested. A CNAME can be mapped to multiple CNAME records in a row, but is not recommended. blog.mydomain.com <--> mydomain.com
| SVR Record | Also known as a service record, these are used to map a domain name to a specific IP address and port number for a serivce. Some services like VIoP require a SRV record be setup. These records include a priority and weight setting to help balance loads between different records associated to the same domain name.
| NS Record| NS stands for nameserver and this type of DNS record is what is used to define what DNS server is authoritative for a particular domain. This record type is used as a means to tell the internet where you can find a specific IP address for a domain. For example, some companies host their own DNS servers with entries to access their resources. They would set an NS record in their larger internet wide DNS provider that points to their DNS server so users can find their domain on the internet.
|SOA Record | This record stands for start of authority and stores important information about a domain like the email adress, when the domain was updated last and how long other DNS servers should wait to try and refresh records from that DNS server. There is a handful of other information we won't cover here included in an SOA record that you can read more about below.
| PRT Record | Also known as a pointer record, this record serves to map a domain name to an IP address. This record is the opposite of a A/AAAA record. The purpose of these records is to allow a DNS reverse lookup where you can do a DNS query on a specific IP address and return a domain name.

If you are curious about more information on any of these domain record types [Cloudflare](https://www.cloudflare.com/learning/dns/dns-records/#:~:text=What%20is%20a%20DNS%20record,handle%20requests%20for%20that%20domain.) has this wonderful article that covers each record type in a lot more detail as well as outlining some of the use cases for each.

<br>
There are a lot more topics to cover within DNS that we will get to in other articles. This article is aimed to give a good basic understanding of some of the core functions of DNS, in other articles we will focus more on some of the inner workings of DNS along with some real world use cases and troubleshooting you can expect to see in an enterprise environment.


## Lets do some exploring
You can lookup DNS records on your own computer to see some of the information that gets returned to it in the background when you type Google.com in your browser. Doing DNS lookups can also be super helpful for troubleshooting networking issues. You can easily determine if an internet issue is caused by DNS or the connection as a whole by pinging an IP address directly and then looking up a DNS entry to see if it returns. Lets try it out.
<br>

Open Command Prompt and type `nslookup Google.com` and press Enter. The nslookup command on Windows is what is used to do an interactive DNS query. You can see there is some data that returns. Showing under the non-authoritative answer you can see there are a handful of IP addresses. The first set are IPv6 addresses. These are configured by Google with an AAAA record. The last IP address is an IPv4 configured with an A record.

<div style=img><img src="/assets/nslookup.png"></div>

<br>

You can also use nslookup to perform a reverse DNS lookup. To do that lets use Google's own DNS server address. In your same commdand prompt window type `nslookup 8.8.8.8`. In the output you will now see that your computer did a DNS query on that IP address and because Google has a PRT record set for that domain, you are able to query the IP address to get the domain name.

<div style=img><img src="/assets/reversedns.png"></div>