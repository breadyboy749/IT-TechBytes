---
layout: post
title:  "Getting Started in IT"
date:   2023-01-01 22:10:56 -0600
categories: GettingStarted_Intro
permalink: /:categories/:title
excerpt: "Introduction to the series. A collection of articles aimed at helping you gain important IT knowledge to land your first job or just learn some stuff about IT and other technologies!"
picture: "/assets/usb-g1939b3231_1920.jpg"
pinned: true
---

<!--<div style="float: right"><img src="/assets/usb-g1939b3231_1920.jpg" width="400" hspace= "20px" vspace="10px" /></div>-->
<div><img src="/assets/usb-g1939b3231_1920.jpg" style="float: right" width="400"></div>



This is the first article in a series aimed to offer guidance, knowledge, and discussion on topics important to starting your IT career. The goal of this series is to provide a single place to read and learn about topics that are necessary when getting started in an enterprise IT envrionment.


\
\
\
\
\
\
\
Below you will find a table that will be updated with all the articles in this series broke out into their respective categories. New articles will be added that cover more in depth topics for each category as time goes on.



|**Intro** | **Excerpt**
|---|---|
{% for post in site.categories.GettingStarted_Intro -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Networking Basics** |
|---|---|
{% for post in site.categories.GettingStarted_NetworkingBasics -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Active Directory** | 
|---|---|
{% for post in site.categories.GettingStarted_ActiveDirectory -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **DNS** | 
|---|---|
{% for post in site.categories.GettingStarted_DNS -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **DHCP** | 
|---|---|
{% for post in site.categories.GettingStarted_DHCP -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Domain Computers** |
|---|---|
{% for post in site.categories.GettingStarted_DomainComputers -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Group Policy** | 
|---|---|
{% for post in site.categories.GettingStarted_GroupPolicy -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Firewalls** | 
|---|---|
{% for post in site.categories.GettingStarted_Firewalls -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Windows Server Administration** | 
|---|---|
{% for post in site.categories.GettingStarted_WindowsServerAdmin -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **PowerShell** | 
|---|---|
{% for post in site.categories.GettingStarted_PowerShell -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **Basic Windows Administration** | 
|---|---|
{% for post in site.categories.GettingStarted_BasicWindowsAdministration -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **PKI** | 
|---|---|
{% for post in site.categories.GettingStarted_PKI -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}
| **O365 Apps** | 
|---|---|
{% for post in site.categories.GettingStarted_O365Apps -%}
{% if post.title -%}
| [{{post.title}}]({{ post.url }}) | {{ post.excerpt }}
{% endif %}
{%- endfor -%}









