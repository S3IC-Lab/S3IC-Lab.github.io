---
layout: page
permalink: /master/
title: Master Students
nav: false
nav_order: 7
display_categories: [Master]
horizontal: false
---

<!-- pages/master.md: grouped by cohort; first cohort open, later cohorts collapsible (toggle on year heading) -->

<div class="projects master-projects">
  {% assign members = site.projects | where: "category", "Master" | sort: "importance" %}
  {% assign prev_cohort = "" %}
  {% assign group_index = 0 %}
  {% for project in members %}
    {% if project.cohort != prev_cohort %}
      {% unless forloop.first %}
    </div>
        {% if group_index > 1 %}</div>{% endif %}
      {% endunless %}
      {% assign cohort_year = project.cohort | split: "." | first %}
      {% assign group_id = "cohort-" | append: cohort_year %}
      {% if group_index == 0 %}
    <h2 class="category">{{ cohort_year }}</h2>
      {% else %}
    <a class="cohort-toggle" data-bs-toggle="collapse" href="#{{ group_id }}" role="button" aria-expanded="false">
      <h2 class="category">{{ cohort_year }}<span class="toggle-arrow">&#9656;</span></h2>
    </a>
    <div class="collapse" id="{{ group_id }}">
      {% endif %}
      {% assign prev_cohort = project.cohort %}
      {% assign group_index = group_index | plus: 1 %}
    <div class="row row-cols-1 row-cols-md-4">
    {% endif %}
    {% include projects.liquid %}
  {% endfor %}
  </div>
  {% if group_index > 1 %}</div>{% endif %}
</div>
