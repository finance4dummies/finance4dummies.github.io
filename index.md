---
layout: default  # Tells Jekyll to use the theme's home layout
author_profile: true  # Shows your author info in sidebar (set to false if unwanted)
---
# Welcome to My Knowledge Base

This is a collection of my notes and insights. Use the search bar above or browse the [archive](/year-archive/).

## Latest Entries
{% for post in site.posts limit:5 %}
  - [{{ post.title }}]({{ post.url | relative_url }}) - {{ post.date | date: "%B %d, %Y" }}
{% endfor %}
