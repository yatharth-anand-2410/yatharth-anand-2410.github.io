---
layout: page
title: "The Experiment Log"
permalink: /blog/
---

Welcome to the log. This is where I document my technical experiments, research findings, and deep-dives into LLM internals. 

---

<div class="posts-list">
  {% for post in site.posts %}
    <div class="post-item" style="margin-bottom: 30px; border-bottom: 1px solid #eee; padding-bottom: 20px;">
      <span class="post-date" style="color: #666; font-size: 0.9em;">{{ post.date | date: "%B %-d, %Y" }}</span>
      <h2 style="margin-top: 5px;"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p style="font-size: 1em; color: #444; line-height: 1.6;">{{ post.excerpt | strip_html | truncatewords: 45 }}</p>
      <a href="{{ post.url | relative_url }}" style="font-weight: bold; color: #007bff;">Read Full Deep-Dive &rarr;</a>
    </div>
  {% endfor %}
</div>
