---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
menu: Home
title: Welcome to IT-TechBytes
---

#### In this blog you will find information on various topics aimed to help you get started in IT. I cover a wide variety of things from all corners of IT to help give you the knowledge to land your first IT job. Startnig with the basics and building off of that to more advanced topics. I also cover security, home networking, home lab, 3D printing, and really anything else I feel like writing about.

<br/>

Check out some of our recent articles, or go on over to the [Blog](http://it-techbytes.com/blog) page to see our Getting Started Series and a list of our other articles.


<style>
.grid-container {
  display: grid;
  grid-template-columns: repeat( 3, 1fr);
  gap: 10px;
  grid-auto-rows: 235px;
  grid-template-areas: "left right";
  padding: 10px;
}

.grid-item {
  border: 3px solid gray;
  background: light gray;
  border-radius: 16px;
  padding: 20px;
  font-size: 30px;
  text-align: center;
  align-items: center;
  display: grid;
  grid-template-columns: repeat(1, 1fr);
}

img {
  max-width: auto;
  height: auto;
}
</style>


#### Recent Articles

<div class="grid-container">


    {% assign latest_post = site.posts[0] %}
    <div class="grid-item"> {{latest_post.title}} </div>
    {% assign latest_post = site.posts[3] %}
    <div class="grid-item"> {{latest_post.title}} </div>
    {% assign latest_post = site.posts[4] %}
    <div class="grid-item"> {{latest_post.title}} <img src = "/assets/WhatisNAT.drawio.png"></div>








</div>