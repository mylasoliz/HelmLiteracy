---
layout: default
title: Finance
permalink: /finance/
---

<div class="page-full">
  <header class="page-header">
    <div class="container">
      <h1 class="page-title">Finance</h1>
      <p style="color:var(--text-muted);margin-top:8px;font-size:0.95rem;">Personal finance, investing basics, and money guides for everyday life.</p>
    </div>
  </header>

  <div class="page-body">
    <div class="container container-narrow">
      {% assign finance_posts = site.posts | where_exp: "post", "post.category contains 'Finance'" %}
      {% assign investing_posts = site.posts | where_exp: "post", "post.category contains 'Investing'" %}
      {% assign finance_posts = finance_posts | concat: investing_posts %}
      {% if finance_posts.size > 0 %}
        <ul class="category-post-list">
          {% for post in finance_posts %}
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
