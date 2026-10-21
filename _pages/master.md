---
layout: page
permalink: /master/
title: Master Students
nav: false
nav_order: 7
display_categories: [Master]
horizontal: false
---

<!-- pages/master.md: grouped by cohort (earlier first), cohort label on divider -->

<div class="projects">
  {% assign members = site.projects | where: "category", "Master" | sort: "cohort" %}
  {% assign prev_cohort = "" %}
  <div class="row row-cols-1 row-cols-md-4">
  {% for project in members %}
    {% unless forloop.first %}
      {% if project.cohort != prev_cohort %}
    </div>
    <div class="d-flex align-items-center my-4">
      <div class="border-top flex-grow-1"></div>
      <span class="mx-3 h5 mb-0">{{ project.cohort }}</span>
      <div class="border-top flex-grow-1"></div>
    </div>
    <div class="row row-cols-1 row-cols-md-4">
      {% endif %}
    {% endunless %}
    {% assign prev_cohort = project.cohort %}
    {% include projects.liquid %}
  {% endfor %}
  </div>
</div>
