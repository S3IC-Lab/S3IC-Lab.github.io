---
layout: page
permalink: /master/
title: Master Students
nav: false
nav_order: 7
display_categories: [Master]
horizontal: false
---

<!-- pages/master.md: grouped by cohort (earlier first), PhD-page style category heading with year only -->

<div class="projects master-projects">
  {% assign members = site.projects | where: "category", "Master" | sort: "importance" %}
  {% assign prev_cohort = "" %}
  {% for project in members %}
    {% if project.cohort != prev_cohort %}
      {% unless forloop.first %}
    </div>
      {% endunless %}
      {% assign cohort_year = project.cohort | split: "." | first %}
    <a id="y{{ cohort_year }}" href=".#y{{ cohort_year }}">
      <h2 class="category">{{ cohort_year }}</h2>
    </a>
    <div class="row row-cols-1 row-cols-md-4">
      {% assign prev_cohort = project.cohort %}
    {% endif %}
    {% include projects.liquid %}
  {% endfor %}
  </div>
</div>
