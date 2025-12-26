---
title: Categories
permalink: /categories/
layout: archive
author_profile: false  # Optional: hides the sidebar author profile
---

{% for category in site.categories %}
  {% assign name = category | first %}
  {% assign posts = category | last %}
  <h2 id="{{ name | slugify }}">{{ name | capitalize }} ({{ posts.size }})</h2>
  <ul>
    {% for post in posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
        <span>{{ post.date | date: "%B %d, %Y" }}</span>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
