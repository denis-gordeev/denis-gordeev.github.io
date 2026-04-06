---
layout: page
title: About
permalink: /about/
---

My name is Denis Gordeev. I work mainly with NLP and Python programming.

This site collects a few longer notes, while shorter updates and links go to my Telegram channel
[`t.me/nlp_party`](https://t.me/nlp_party).

## What this site contains

- Blog posts with technical notes and small repository updates.
- A compact set of public links for people who want a quick overview.
- Occasional `AUTOWORK` entries documenting maintenance changes made in this repository.

## Links

- Telegram: [`t.me/nlp_party`](https://t.me/nlp_party)
- GitHub: [`github.com/denis-gordeev`](https://github.com/denis-gordeev)
- CV: [English PDF](/cvs/Gordeev_en_2022.pdf)
- Blog archive: [all posts](/archive/)

## Recent post

{% assign latest_post = site.posts.first %}
{% assign autowork_posts = site.posts | where_exp: "post", "post.title contains 'AUTOWORK'" %}
{% assign latest_autowork_post = autowork_posts.first %}
{% assign latest_technical_post = nil %}
{% for post in site.posts %}
{% unless post.title contains 'AUTOWORK' %}
{% assign latest_technical_post = post %}
{% break %}
{% endunless %}
{% endfor %}
{% if latest_post %}
- [{{ latest_post.title }}]({{ latest_post.url | relative_url }}) from {{ latest_post.date | date: "%B %-d, %Y" }}
{% endif %}

## Latest technical note

{% if latest_technical_post %}
- [{{ latest_technical_post.title }}]({{ latest_technical_post.url | relative_url }}) from {{ latest_technical_post.date | date: "%B %-d, %Y" }}
{% endif %}

## Latest repository update

{% if latest_autowork_post %}
- [{{ latest_autowork_post.title }}]({{ latest_autowork_post.url | relative_url }}) from {{ latest_autowork_post.date | date: "%B %-d, %Y" }}
{% endif %}
