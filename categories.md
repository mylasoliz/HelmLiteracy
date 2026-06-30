---
layout: default
title: Categories
permalink: /categories/
---

<div class="page-full">
  <header class="page-header">
    <div class="container">
      <h1 class="page-title">Categories</h1>
    </div>
  </header>

  <div class="page-body">
    <div class="container container-narrow">

      {% assign categories = site.posts | map: "category" | uniq | sort %}
      {% for category in categories %}
        {% if category %}
        <div class="category-section">
          <h2>{{ category }}</h2>
          <ul class="category-post-list">
            {% for post in site.posts %}
              {% if post.category == category %}
              <li class="category-post-item">
                <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
                <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %-d, %Y" }}</time>
              </li>
              {% endif %}
            {% endfor %}
          </ul>
        </div>
        {% endif %}
      {% endfor %}

    </div>
  </div>
</div>
