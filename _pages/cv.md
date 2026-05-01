---
layout: page
permalink: /cv/
title: cv
nav: true
nav_order: 3
cv_pdf: /assets/pdf/CV_Minjun_Kang.pdf
description: A summary of my education, professional experience, awards, and academic activities.
toc:
  sidebar: left
---

<div class="cv">
  {% for data in site.data.cv %}
    <div class="card mt-3 p-3">
      <h3 class="card-title font-weight-medium">{{ data.title }}</h3>
      <div>
        {% if data.type == "list" %}
          {% include cv/list.liquid %}
        {% elsif data.type == "map" %}
          {% include cv/map.liquid %}
        {% elsif data.type == "nested_list" %}
          {% include cv/nested_list.liquid %}
        {% elsif data.type == "time_table" %}
          {% include cv/time_table.liquid %}
        {% else %}
          {{ data.contents }}
        {% endif %}
      </div>
    </div>
  {% endfor %}
</div>
