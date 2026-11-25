---
layout: default
title: Writing
permalink: /blog/
---
<div class="prose">
  <div class="eyebrow">Technical writing</div>
  <h1>Writing</h1>
  <p>Notes and practical investigations on C++, Windows systems engineering, and reliable software.</p>
  {% for post in site.posts %}
  <div class="item"><div class="meta">{{ post.date | date: '%B %-d, %Y' }}</div><h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3><p>{{ post.description }}</p></div>
  {% endfor %}
</div>
