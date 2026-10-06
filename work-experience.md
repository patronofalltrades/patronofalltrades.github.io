---
layout: page
title: Work Experience
description: "Scaled a VR edtech startup to $1M+ revenue and 50+ factory clients across SEA."
permalink: /work-experience/
---
{% comment %} Work Experience page. The jobs come from _data/experience.yml. {% endcomment %}

<ol class="experience-list">
  {% for role in site.data.experience %}
  <li class="experience-item">
    <div class="experience-date">
      <time datetime="{{ role.start_date }}">{{ role.start_label }}</time>
      <span aria-hidden="true"> – </span>
      <time datetime="{{ role.end_date }}">{{ role.end_label }}</time>
      <span class="meta-separator" aria-hidden="true"> · </span>{{ role.location }}
    </div>
    <div class="experience-detail">
      <h2>{{ role.title | escape }} — {{ role.company | escape }} ({{ role.legal_entity | escape }})</h2>
      <p class="experience-summary">{{ role.summary }}</p>
      <ul class="achievement-list">
        {% for achievement in role.achievements %}
        <li>{{ achievement }}</li>
        {% endfor %}
      </ul>
      <ul class="tag-list" aria-label="Role focus areas">
        {% for tag in role.tags %}
        <li>{{ tag }}</li>
        {% endfor %}
      </ul>
    </div>
  </li>
  {% endfor %}
</ol>
