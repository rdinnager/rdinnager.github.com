---
layout: page
title: Open Science Notebook
tagline: for Russell Dinnage
---
{% include JB/setup %}

Welcome to my Open Science Notebook. This is where I keep all my day-to-day noted for my scientific work in ecology. It is mainly for my own benefit, but there may be some things of use or interest to other people. Feel free to use whatever you like (with attribution please!). Also, please get in touch if you see anything interesting here that you would like to talk about.

#Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a><br>
    {% include postexcerpt.html %}</li>
  {% endfor %}
</ul>
