---
layout: post
title: "Archives"
author: "The Staff"
permalink: /archives/
--- 
{% assign postsByYear =
    site.posts | group_by_exp:"post", "post.date | date: '%Y'" %}
{% for year in postsByYear %}
  <h1>{{ year.name }}</h1>
    <ul>
      {% for post in year.items %}
        <li><a href="{{ post.url }}">{{ post.title }}-{{ post.date }}</a></li>
      {% endfor %}
    </ul>
{% endfor %}
