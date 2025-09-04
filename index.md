---
layout: default
title: Home
---

<section class="hero">
  <h1>Greetings, one and all!</h1>
  <p>I'm Alan — an orchestra-conductor-turned-penetration tester…</p>
  <p><a href="/blog/">Browse latest posts</a> · <a href="/walkthroughs/">Featured walkthroughs</a></p>
</section>

<h2>Latest posts</h2>
<ul>
  {% for post in site.posts limit:4 %}
  <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a> — {{ post.date | date: "%b %d, %Y" }}</li>
  {% endfor %}
</ul>

{% assign feat = site.posts | where_exp: "p", "p.tags contains 'walkthrough'" | last %}
{% if feat %}
<h2>Featured walkthrough</h2>
<p><a href="{{ feat.url | relative_url }}">{{ feat.title }}</a></p>
{% endif %}

<h2>Resources</h2>
<ul>
  <li><a href="/learn/#waf-notes">WAF notes</a></li>
  <li><a href="/learn/#cheatsheets">Cheat sheets</a></li>
  <li><a href="/learn/#tools">Tools & PoCs</a></li>
</ul>
