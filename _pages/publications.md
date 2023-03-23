---
layout: page
permalink: /publications/
title: publications
years: [2019]
nav: true
nav_order: 1
---
<!-- _pages/publications.md -->
<!-- <div class="publications"> -->

<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
      {% include selected_papers.html %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {% include selected_papers.html %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {% include selected_papers.html %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {% include selected_papers.html %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>

<!-- </div> -->
