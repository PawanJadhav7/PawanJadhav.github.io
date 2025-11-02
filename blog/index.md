---
layout: default
title: Blog
permalink: /blog/
---

# Blog

{% for post in site.posts %}
- **[{{ post.title }}]({{ post.url | relative_url }})**  
  <small>{{ post.date | date: "%B %d, %Y" }}</small><br/>
  {{ post.excerpt | strip_html | truncate: 150 }}
{% endfor %}
