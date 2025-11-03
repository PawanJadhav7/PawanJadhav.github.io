---
layout: default
title: Blog
permalink: /blog/
---
<p style="margin:16px 0;">
  <a href="/" class="btn" style="display:inline-flex;align-items:center;gap:6px;
      padding:6px 12px;border-radius:8px;border:1px solid #e5e7eb;
      background:#f8fafc;color:#111827;text-decoration:none;font-size:14px;">
    ← Back to Home
  </a>
</p>
# Blog

{% for post in site.posts %}
- **[{{ post.title }}]({{ post.url | relative_url }})**  
  <small>{{ post.date | date: "%B %d, %Y" }}</small><br/>
  {{ post.excerpt | strip_html | truncate: 150 }}
{% endfor %}
