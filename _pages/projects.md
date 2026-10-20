---
layout: page
title: Projects
permalink: /projects/
description: Selected research projects and open-source tools.
nav: true
nav_order: 4
display_categories: [grants, software]
horizontal: false
---

<style>
  /* Make the category labels readable section headings (the theme draws them in the
     faint divider colour, right-aligned) and keep card titles to card size. */
  .projects h2.category {
    color: var(--global-text-color);
    text-align: left;
    text-transform: capitalize;
    font-size: 1.35rem;
    margin-top: 1.6rem;
    padding-bottom: 0.3rem;
  }
  .projects .card .card-title { font-size: 1.2rem; line-height: 1.35; }
  .projects .card .card-text { font-size: 0.88rem; color: var(--global-text-color-light); }
</style>

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
