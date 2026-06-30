---
layout: default
title: AI
permalink: /ai/
---

<div class="page-full">
  <header class="page-header">
    <div class="container">
      <h1 class="page-title">AI</h1>
      <p style="color:var(--text-muted);margin-top:8px;font-size:0.95rem;">Tools, literacy, and practical guides for navigating artificial intelligence.</p>
    </div>
  </header>

  <div class="page-body">
    <div class="container container-narrow">
      {% assign ai_posts = site.posts | where_exp: "post", "post.category contains 'AI'" %}
      {% if ai_posts.size > 0 %}
        <ul class="category-post-list">
          {% for post in ai_posts %}
          <li class="category-post-item">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %-d, %Y" }}</time>
          </li>
          {% endfor %}
        </ul>
      {% else %}
        <p style="color:var(--text-muted);">Posts coming soon.</p>
      {% endif %}
    </div>
  </div>
</div>
