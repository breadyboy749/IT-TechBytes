---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: page
menu: Home
title: Welcome to IT-TechBytes
---

#### In this blog you will find information on various topics aimed to help you get started in IT. I cover a wide variety of things from all corners of IT to help give you the knowledge to land your first IT job. Starting with the basics and building off of that to more advanced topics. I also cover security, home networking, home lab, 3D printing, and really anything else I feel like writing about. 
#### I am by no means an expert in any of these fields, but I want to share the knowledge and experience I have gathered taking on various roles and responsibilites in my career thus far.

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