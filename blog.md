---
layout: default
title: Blog
permalink: /blog/
---

<span class="eyebrow">Blog</span>
# Blog

{% assign blog_posts = site.pages | where_exp: "item", "item.path contains 'posts/'" %}

<section class="blog-list">
  {% for post in blog_posts %}
    <article class="blog-card">
      <div class="blog-card-copy">
        <div class="blog-card-title">{{ post.title }}</div>
        <p>{{ post.description | default: post.excerpt | strip_html }}</p>
      </div>
      <a class="blog-read-link" href="{{ post.url | relative_url }}">Read</a>
    </article>
  {% endfor %}
</section>
