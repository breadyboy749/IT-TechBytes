---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
menu: Home
title: Welcome to IT-TechBytes
---

#### In this blog you will find information on various topics aimed to help you get started in IT. I cover a wide variety of things from all corners of IT to help give you the knowledge to land your first IT job. Starting with the basics and building off of that to more advanced topics. I also cover security, home networking, home lab, 3D printing, and really anything else I feel like writing about. 
#### As time goes on you always learn, adapt, and discover new things and I want to share the knowledge and experience I have gathered taking on various roles and responsibilites in my career thus far.

<br/>

Check out some of our recent articles, or go on over to the [Blog](http://it-techbytes.com/blog) page to see our Getting Started Series and a list of our other articles.


# Recent Articles
<style>
@media screen and (min-width: 40em) {
.body {
  display: flex;
  flex-wrap: wrap;
  
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
  height: 450px;
}

.card img {
  object-fit: cover;
  height: 200px;
  border-radius: 8px 8px 0 0; /* Rounded corners at the top */
}

.card:hover {
  transform: scale(1.05);
}


/* Add some padding inside the card container */
.container {
  padding: .1px 10px;
  flex: 1;
}

.container h3 {
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.blah {
  padding: 10px;
  object-fit: cover;
  

}

</style>



<div class="body">
  {% assign latest_post = site.posts[0] %}
  <a href="{{site.baseurl}}{{latest_post.url}}" class="card">
    <div class="blah"><img src= "{{latest_post.picture}}" style="width:100%"></div>
    <div class="container">
      <h3><b>{{latest_post.title}}</b></h3>
      <p>{{latest_post.excerpt}}</p>
    </div>
  </a>
  {% assign latest_post = site.posts[1] %}
  <a href="{{site.baseurl}}{{latest_post.url}}" class="card">
    <div class="blah"><img src="{{latest_post.picture}}" style="width:100%"></div>
    <div class="container">
      <h3><b>{{latest_post.title}}</b></h3>
      <p>{{latest_post.excerpt}}</p>
    </div>
  </a>
  {% assign latest_post = site.posts[2] %}
  <a href="{{site.baseurl}}{{latest_post.url}}" class="card">
    <div class="blah"><img src="{{latest_post.picture}}" style="width:100%"></div>
    <div class="container">
      <h3><b>{{latest_post.title}}</b></h3>
      <p>{{latest_post.excerpt}}</p>
    </div>
  </a>
</div>