---
layout: page
permalink: /master/
title: Master Students
nav: false
nav_order: 7
display_categories: [Master]
horizontal: false
---

<!-- pages/master.md: grouped by cohort; within each group show first 4 members, rest behind a collapse toggle -->

<div class="projects master-projects">
  {% assign members = site.projects | where: "category", "Master" | sort: "importance" %}
  {% assign prev_cohort = "" %}
  {% assign pos = 0 %}
  {% assign collapse_open = false %}
  {% for project in members %}
    {% if project.cohort != prev_cohort %}
      {% unless forloop.first %}
        {% if collapse_open %}
    </div>
    </div>
        {% else %}
    </div>
        {% endif %}
      {% endunless %}
      {% assign cohort_year = project.cohort | split: "." | first %}
    <h2 class="category">{{ cohort_year }}</h2>
    <div class="row row-cols-1 row-cols-md-4">
      {% assign prev_cohort = project.cohort %}
      {% assign pos = 0 %}
      {% assign collapse_open = false %}
    {% endif %}
    {% if pos == 4 %}
    </div>
    <div class="text-center my-3">
      <a class="cohort-toggle" data-toggle="collapse" href="#more-{{ cohort_year }}" role="button" aria-expanded="false"><span class="toggle-arrow">&#9656;</span> More</a>
    </div>
    <div class="collapse" id="more-{{ cohort_year }}">
    <div class="row row-cols-1 row-cols-md-4">
      {% assign collapse_open = true %}
    {% endif %}
    {% include projects.liquid %}
    {% assign pos = pos | plus: 1 %}
  {% endfor %}
  {% if collapse_open %}
    </div>
    </div>
  {% else %}
    </div>
  {% endif %}
</div>
