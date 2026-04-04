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
- Archive: [all blog posts](/archive/)
- CV: [English PDF](/cvs/Gordeev_en_2022.pdf)
- Telegram: [`t.me/nlp_party`](https://t.me/nlp_party)
{% if latest_post %}
- Latest post: [{{ latest_post.title }}]({{ latest_post.url | relative_url }}) from {{ latest_post.date | date: "%B %-d, %Y" }}
{% endif %}

## What you will find here

- Short technical notes on Python, NLP, and developer tooling.
- Repository maintenance updates marked with `AUTOWORK` in the title.
- Links to longer background material such as the CV and external profiles.

## Start here

If you are new to the site, start with the [About page](/about/) for the main links and then check the blog feed
below for the newest note or maintenance update. If you want a compact chronological list, open the
[archive page](/archive/).
