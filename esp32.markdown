---
layout: page
title: ESP32
permalink: /esp32/
---

<div class="posts">
    {% assign sorted-posts = site.posts | where: "categories","esp32" %}
    {% for post in sorted-posts %}

        {%- assign date_format = site.minima.date_format | default: "%b %-d" -%}
        {%- assign week_format = "Week " | append: post.week -%}

        <h3>{{ week_format }}, {{ post.date | date: date_format }}: <a href="{{ post.url }}">{{ post.title }}</a></h3>

{% endfor %}
</div>


