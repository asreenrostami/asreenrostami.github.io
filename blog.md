---
layout: default
title: Blog
permalink: /blog/
---

<ul class="post-list">
  {% for post in site.posts %}
  <li>
    <span class="post-date">{{ post.date | date: "%B %-d, %Y" }}</span>
    <a href="{{ post.url | relative_url }}"><h3 class="mb-0">{{ post.title }}</h3></a>
    {% if post.excerpt %}<p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>{% endif %}
  </li>
  {% else %}
  <li><em>No posts yet &mdash; check back soon.</em></li>
  {% endfor %}
</ul>
