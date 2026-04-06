---
layout: page
title: Denis Gordeev
---

{% assign latest_post = site.posts.first %}
{% assign recent_posts = site.posts | slice: 0, 4 %}
{% assign autowork_posts = site.posts | where_exp: "post", "post.title contains 'AUTOWORK'" %}
{% assign latest_autowork_post = autowork_posts.first %}
{% assign latest_technical_post = nil %}
{% for post in site.posts %}
  {% unless post.title contains 'AUTOWORK' %}
    {% assign latest_technical_post = post %}
    {% break %}
  {% endunless %}
{% endfor %}

<section class="hero-panel">
  <p class="hero-kicker">NLP, Python, and public notes</p>
  <p class="hero-summary">
    I am Denis Gordeev. This site is a compact index of technical notes, repository updates, and public links.
    Shorter updates go to <a href="https://t.me/nlp_party"><code>t.me/nlp_party</code></a>.
  </p>

  <div class="quick-links">
    <a class="quick-link-card" href="/about/">
      <strong>About</strong>
      <span>Profile, links, and a quick starting point.</span>
    </a>
    <a class="quick-link-card" href="/archive/">
      <strong>Archive</strong>
      <span>Chronological list of all blog posts.</span>
    </a>
    <a class="quick-link-card" href="/cvs/Gordeev_en_2022.pdf">
      <strong>CV</strong>
      <span>Public English PDF version.</span>
    </a>
  </div>
</section>

<section class="home-section">
  <h2>What is here</h2>
  <ul class="feature-list">
    <li>Short technical notes on Python, NLP, and developer tooling.</li>
    <li>Repository maintenance updates marked with <code>AUTOWORK</code> in the title.</li>
    <li>Stable public links for people who want a quick overview.</li>
  </ul>
</section>

<section class="home-section">
  <h2>Recent posts</h2>
  {% if latest_post %}
  <p class="latest-post-note">
    Latest update:
    <a href="{{ latest_post.url | relative_url }}">{{ latest_post.title }}</a>
    <span>{{ latest_post.date | date: "%B %-d, %Y" }}</span>
  </p>
  {% endif %}

  <ul class="post-list compact-post-list">
    {% for post in recent_posts %}
    <li>
      <span class="post-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      <p class="post-summary">
        {{ post.excerpt | strip_html | normalize_whitespace | truncatewords: 28 }}
      </p>
    </li>
    {% endfor %}
  </ul>

  <p class="archive-callout">
    For the full chronology, use the <a href="/archive/">archive page</a>.
  </p>
</section>

{% if latest_technical_post %}
<section class="home-section">
  <h2>Latest technical note</h2>
  <p class="latest-post-note">
    <a href="{{ latest_technical_post.url | relative_url }}">{{ latest_technical_post.title }}</a>
    <span>{{ latest_technical_post.date | date: "%B %-d, %Y" }}</span>
  </p>
  <p class="post-summary">
    {{ latest_technical_post.excerpt | strip_html | normalize_whitespace | truncatewords: 26 }}
  </p>
</section>
{% endif %}

{% if latest_autowork_post %}
<section class="home-section">
  <h2>Latest repository update</h2>
  <p class="latest-post-note">
    <a href="{{ latest_autowork_post.url | relative_url }}">{{ latest_autowork_post.title }}</a>
    <span>{{ latest_autowork_post.date | date: "%B %-d, %Y" }}</span>
  </p>
  <p class="post-summary">
    {{ latest_autowork_post.excerpt | strip_html | normalize_whitespace | truncatewords: 26 }}
  </p>
</section>
{% endif %}
