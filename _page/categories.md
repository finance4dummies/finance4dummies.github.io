---
title: Categories
permalink: /categories/
layout: archive
author_profile: false
---

<h1 class="page__title">Categories</h1>

{% assign categories = site.posts | map: 'categories' | join: ',' | split: ',' | uniq %}

{% for category in categories %}
  {% assign category_name = category | strip %}
  {% if category_name != '' %}
    {% assign posts_in_category = site.posts | where_exp: "post", "post.categories contains category_name" %}
    <h2 id="{{ category_name | slugify }}" class="archive__subtitle">
      {{ category_name | capitalize }} ({{ posts_in_category.size }})
    </h2>
    <ul class="taxonomy__index">
      {% for post in posts_in_category %}
        <li>
          <a href="{{ post.url | relative_url }}">
            <strong>{{ post.title }}</strong>
            <span class="archive__item-date">{{ post.date | date: "%B %d, %Y" }}</span>
          </a>
        </li>
      {% endfor %}
    </ul>
  {% endif %}
{% endfor %}
