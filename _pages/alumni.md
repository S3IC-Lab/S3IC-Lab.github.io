---
layout: page
permalink: /alumni/
title: Alumni
description:
nav: false
nav_order: 7
display_categories: []
horizontal: false
---

<div class="projects master-projects">
  {% assign alumni = site.projects | where: "category", "Alumni" | sort: "importance" %}
  {% if alumni.size > 0 %}
  <h2 class="category">Ph.D. at HKUST (GZ)</h2>
  <div class="row row-cols-1 row-cols-md-4">
    {% for project in alumni %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
</div>

##### Post-doc Researchers

---

- Dr. **Jinbao Zhu**, 2021.8-2023.8, now assistant professor at **Southwest Jiaotong University**.

##### Master Students

---

- **Jin Liu**, 2022.9-2024.6.
- **Mingzhe Liu**, 2022.9-2024.6.
- **Junru Lin**, 2022.9-2024.6.
- **Mengqi Chen**, 2022.9-2024.6.
- **Jiaxiang Tang**, 2021.9-2023.6, now pursing PhD at **University of Minnesota Twin Cities**.

##### Visiting Students

---

- **Jiacheng Liang**, 2021 spring, now pursing PhD at **Penn State**.

##### Research Assistants

---

- **Siyang Jiang**, 2021 fall, now pursing PhD at **CUHK**.
