---
layout: default
title: Blog
permalink: /blog/
---

<span class="eyebrow">Blog</span>
# Blog

This section contains markdown posts from the `posts` folder. Each card shows the post title and a short summary, and the `Read` button opens the full article page.

{% assign blog_posts = site.pages | where_exp: "item", "item.dir == '/posts/'" | sort: "title" %}

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
