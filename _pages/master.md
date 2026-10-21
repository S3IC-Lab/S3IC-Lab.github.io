---
layout: page
permalink: /master/
title: Master Students
nav: false
nav_order: 7
display_categories: [Master]
horizontal: false
---

<!-- pages/master.md: grouped by cohort (earlier first), divider between cohorts -->

<div class="projects">
  {% assign members = site.projects | where: "category", "Master" | sort: "cohort" %}
  {% assign prev_cohort = "" %}
  <div class="row row-cols-1 row-cols-md-4">
  {% for project in members %}
    {% unless forloop.first %}
      {% if project.cohort != prev_cohort %}
    </div>
    <hr>
    <div class="row row-cols-1 row-cols-md-4">
      {% endif %}
    {% endunless %}
    {% assign prev_cohort = project.cohort %}
    {% include projects.liquid %}
  {% endfor %}
  </div>
</div>
