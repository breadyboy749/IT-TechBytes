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
  /* Add shadows to create the "card" effect */
  box-shadow: 0 4px 8px 0 rgba(245, 245, 245, 0.2);
  background-color: rgb(64, 64, 64);
  border-radius: 5px;
  transition: 0.3s;
  display: flex;
  flex-flow: row wrap;
  flex-direction: column ;
  text-align: left;
  align-items: left;
  flex: 31%;
  margin: 8px;


}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
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