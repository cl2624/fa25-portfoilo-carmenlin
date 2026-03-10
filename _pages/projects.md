---
layout: default
title: Carmen Lin - Portfolio
permalink: /projects/
---

<div class="gallery-container">
  <div class="project-gallery">
    {% for project in site.projects %}
      <div class="gallery-item">
        <a href="{{ project.url | relative_url }}">
          <img src="{{ project.image | relative_url }}" alt="{{ project.title }}">
        </a>
        <p>{{ project.title }}</p>
      </div>
    {% endfor %}
  </div>
</div>