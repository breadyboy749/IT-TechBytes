---
layout: blog
title: Blog
permalink: /blog/
menu: Blog
---

# Pinned Posts


<div class="articles-container">
{% for post in site.posts %}
    {% if post.pinned == true %}
      <a href="{{site.baseurl}}{{post.url}}" class="card">
        <img src="{{ post.picture }}" alt="{{ post.title }}">
        <div class="card-content">
          <h3>{{ post.title }}</h3>
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
/* Set the background color */
body {
  font-family: 'Roboto', sans-serif;
  color: #ddd;
  margin: 0;
  padding: 0;
}

/* Proper 3-column grid layout */
.articles-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr)); /* Ensures 3 columns where possible */
  gap: 20px; /* Adds spacing between items */
  max-width: 1200px;
  margin: auto;
  padding: 20px;
}

/* Responsive Design: 1-2 columns for smaller screens */
@media (max-width: 1024px) {
  .articles-container {
    grid-template-columns: repeat(2, 1fr);
  }
}
@media (max-width: 768px) {
  .articles-container {
    grid-template-columns: 1fr;
  }
}

/* Card Styling */
.card {
  background-color: rgb(50, 50, 50); /* Dark background for contrast */
  border-radius: 12px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
  transition: box-shadow 0.3s ease-in-out, transform 0.2s ease-in-out;
  text-decoration: none;
  display: flex;
  flex-direction: column;
  overflow: hidden;
  border: 1px solid #444;
  height: 100%; /* Ensures uniform height */
}

/* Image Styling */
.card img {
  width: 100%;
  height: 180px;
  object-fit: cover;
  display: block; /* Fixes any extra spacing */
}

/* Hover Effect */
.card:hover {
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.4);
  transform: translateY(-3px);
}

/* Card Content */
.card-content {
  padding: 16px;
  display: flex;
  flex-direction: column;
  gap: 8px;
  flex-grow: 1; /* Ensures content fills the card */
}

/* Title Styling */
.card-content h3 {
  font-size: 1.4rem;
  font-weight: 600;
  color: #fff;
  margin: 0;
  line-height: 1.3;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

/* Article Intro */
.card-content p {
  font-size: 1rem;
  color: #bbb;
  margin: 0;
  line-height: 1.6;
  height: 48px; /* Keeps text aligned properly */
  overflow: hidden;
}

/* Button Section (Fixes Read More button alignment) */
.card-action {
  padding: 16px;
  text-align: center;
  margin-top: auto; /* Pushes button to bottom */
  width: 100%; /* Ensures it doesn’t cause overflow */
  display: flex;
  justify-content: center;
}

/* Read More Link (Fixed) */
.card-action a {
  text-decoration: none;
  font-size: 1rem;
  font-weight: 500;
  color: #4da6ff;
  display: inline-block; /* Ensure it doesn't break layout */
  text-align: center;
  padding: 10px 20px;
  border-radius: 8px;
  background: rgba(77, 166, 255, 0.1);
  transition: background 0.3s ease-in-out, color 0.3s ease-in-out;
}

/* Remove underline & fix hover */
.card-action a:hover {
  background: rgba(77, 166, 255, 0.2);
  color: #66c2ff;
}
</style>

<!-- Dynamic Jekyll Blog Post Cards -->
<div class="articles-container">
  {% assign posts = site.posts | slice: 3, site.posts.size %}
  {% for post in posts limit: 4 %}
  <a href="{{ site.baseurl }}{{ post.url }}" class="card">
    <img src="{{ post.picture }}" alt="{{ post.title }}">
    <div class="card-content">
      <h3>{{ post.title }}</h3>
      <p>{{ post.excerpt }}</p>
    </div>
  </a>
  {% endfor %}
</div>

<br/>
<br/>

# All Blog Posts