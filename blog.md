---
layout: blog
title: Blog
permalink: /blog/
menu: Blog
---

# Pinned Posts


<div class="body">
{% for post in site.posts %}
    {% if post.pinned == true %}
      <a href="{{site.baseurl}}{{post.url}}" class="card">
        <div class="blah"><img src= "{{post.picture}}" style="width:100%"></div>
        <div class="container">
          <h3><b>{{post.title}}</b></h3>
          <p>{{post.excerpt}}</p>
        </div>
      </a>
          {% endif %}
          {% endfor %}
</div>


<br>
<br>

# More Recent Posts

<style>
@media screen and (min-width: 40em) {
.body {
  display: flex;
  flex-direction: row;

}

}

.card {
  background-color: rgb(64, 64, 64); /* Use a light background color */
  border-radius: 8px;
  transition: transform 0.3s ease-in-out;
  display: flex;
  flex-direction: row wrap;
  flex-direction: column;
  text-align: left;
  margin: 8px;
  overflow: hidden;
  flex: 31%;
  height: 400px;
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  transform: scale(1.05);
}

.card img {
  object-fit: cover;
  height: 200px;
  border-radius: 8px 8px 0 0; /* Rounded corners at the top */
}

/* Add some padding inside the card container */
.container {
  padding: 10px 10px;

}

.blah {
  padding: 10px;
  object-fit: cover;
  

}

</style>



<div class="body">
  {% assign latest_post = site.posts[3] %}
  <a href="{{site.baseurl}}{{latest_post.url}}" class="card">
    <div class="blah"><img src= "{{latest_post.picture}}" style="width:100%"></div>
    <div class="container">
      <h3><b>{{latest_post.title}}</b></h3>
      <p>{{latest_post.excerpt}}</p>
    </div>
  </a>
  {% assign latest_post = site.posts[4] %}
  <a href="{{site.baseurl}}{{latest_post.url}}" class="card">
    <div class="blah"><img src="{{latest_post.picture}}" style="width:100%"></div>
    <div class="container">
      <h3><b>{{latest_post.title}}</b></h3>
      <p>{{latest_post.excerpt}}</p>
    </div>
  </a>
  {% assign latest_post = site.posts[5] %}
  <a href="{{site.baseurl}}{{latest_post.url}}" class="card">
    <div class="blah"><img src="{{latest_post.picture}}" style="width:100%"></div>
    <div class="container">
      <h3><b>{{latest_post.title}}</b></h3>
      <p>{{latest_post.excerpt}}</p>
    </div>
  </a>
</div>

<br/>
<br/>

# All Blog Posts