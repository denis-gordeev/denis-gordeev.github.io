---
layout: page
title: Archive
permalink: /archive/
---

{% assign autowork_posts = site.posts | where_exp: "post", "post.title contains 'AUTOWORK'" %}

## Technical notes

{% for post in site.posts %}
{% unless post.title contains 'AUTOWORK' %}
- <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span> [{{ post.title }}]({{ post.url | relative_url }})
  <p class="post-summary">
    {{ post.excerpt | strip_html | normalize_whitespace | truncatewords: 32 }}
  </p>
{% endunless %}
{% endfor %}

## AUTOWORK updates

{% for post in autowork_posts %}
- <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span> [{{ post.title }}]({{ post.url | relative_url }})
  <p class="post-summary">
    {{ post.excerpt | strip_html | normalize_whitespace | truncatewords: 32 }}
  </p>
{% endfor %}
