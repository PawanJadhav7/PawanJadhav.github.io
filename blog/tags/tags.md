---
layout: default
title: Tags
permalink: /tags/
---

<h1>Tags</h1>

<ul class="tag-cloud">
  {% assign tags = site.tags | sort %}
  {% for tag in tags %}
    <li>
      <a href="#{{ tag[0] | slugify }}">#{{ tag[0] }}</a>
      <span class="tag-count">{{ tag[1].size }}</span>
    </li>
  {% endfor %}
</ul>

<hr/>

{% for tag in site.tags %}
  <section id="{{ tag[0] | slugify }}" class="tag-section">
    <h2>#{{ tag[0] }}</h2>
    <ul class="tag-posts">
      {% assign posts = tag[1] | sort: 'date' | reverse %}
      {% for post in posts %}
        <li>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          <small>— {{ post.date | date: "%b %d, %Y" }}</small>
          {% if post.excerpt %}<div class="tag-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</div>{% endif %}
        </li>
      {% endfor %}
    </ul>
  </section>
{% endfor %}
