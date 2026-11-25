---
layout: default
title: Home
---

<section class="hero">
  <div class="eyebrow">C++ · Windows · Systems Engineering</div>
  <h1>Building reliable software close to the system.</h1>
  <p class="lead">I'm Pedro Bonifácio, a C++ systems engineer working on native Windows software and endpoint security. I write about debugging, concurrency, networking, secure communication, and the trade-offs behind maintainable systems.</p>
  <div class="actions"><a class="button primary" href="{{ '/blog/' | relative_url }}">Read the blog</a><a class="button secondary" href="{{ '/projects/' | relative_url }}">Explore projects</a></div>
</section>

<section class="section">
  <h2>Areas I explore</h2>
  <div class="cards">
    <div class="card"><div class="tag">01 / Windows</div><h3>Windows internals</h3><p>Native services, APIs, telemetry, system lifecycle, and reliability.</p></div>
    <div class="card"><div class="tag">02 / C++</div><h3>Concurrency & debugging</h3><p>Failure analysis, threading, resource ownership, and performance.</p></div>
    <div class="card"><div class="tag">03 / Distributed systems</div><h3>Secure communication</h3><p>gRPC, TLS, network protocols, cancellation, and fault handling.</p></div>
  </div>
</section>

<section class="section">
  <h2>Recent writing</h2>
  {% assign latest_posts = site.posts | slice: 0, 3 %}
  {% for post in latest_posts %}<div class="item"><div class="meta">{{ post.date | date: '%B %-d, %Y' }}</div><h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3><p>{{ post.description }}</p></div>{% endfor %}
</section>
