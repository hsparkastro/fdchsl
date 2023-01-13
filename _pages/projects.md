---
layout: page
title: Research
permalink: /projects/
description:
nav: true
nav_order: 1
display_categories: 
horizontal: false
---

Our lab focuses on two directions: 
- **Fundamental research** on intelligent and high assurance autonomy for the Cyber-Physical System (CPS)
  
  CPS is a complex (networked) system with interacting physical and logical components, using hybrid systems theory. Aerospace systems are good examples of the CPS. For example, an Unmanned Aircraft System (UAS), or similarly, aircraft and spacecraft, is composed of an autopilot which is a logical element and a vehicle that is a physical element, thus it is a CPS.

- **Applications to safety-critical aerospace systems** such as 
  - Aircraft, spacecraft, UAS, and multiple-vehicle systems (e.g., swarm of UAS)
  - Air Traffic Control (ATC) including UAS traffic management
  - Space applications


<!-- pages/projects.md -->
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
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
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
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
