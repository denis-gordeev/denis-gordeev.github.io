---
layout: page
title: Archive
permalink: /archive/
---

## All posts

{% for post in site.posts %}
- <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span> [{{ post.title }}]({{ post.url | relative_url }})
  <p class="post-summary">
    {{ post.excerpt | strip_html | normalize_whitespace | truncatewords: 32 }}
  </p>
{% endfor %}
