---
layout: home
title: Denis Gordeev
---

{% assign latest_post = site.posts.first %}

I am Denis Gordeev. I work mainly with NLP and Python programming.

This site is a small archive of notes, links, and blog posts. For shorter updates, see my Telegram channel
[`t.me/nlp_party`](https://t.me/nlp_party). For background information, visit the [About page](/about/).

## Highlights

- About: [short profile and links](/about/)
- CV: [English PDF](/cvs/Gordeev_en_2022.pdf)
- Telegram: [`t.me/nlp_party`](https://t.me/nlp_party)
{% if latest_post %}
- Latest post: [{{ latest_post.title }}]({{ latest_post.url | relative_url }}) from {{ latest_post.date | date: "%B %-d, %Y" }}
{% endif %}
