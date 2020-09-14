---
layout: page
title: "intro"
permalink: /intro/
---

<div class="posts">
    {% assign sorted-posts = site.posts | where: "categories","intro" %}
    {% for post in sorted-posts %}
    {% assign date_format = "Week " | append: post.week | append: " " %}

        <h3>{{ date_format }} <a href="{{ post.url }}">{{ post.title }}</a></h3>

{% endfor %}
</div>

