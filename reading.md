---
layout: page
title: "Reading"
description: "Essays and books that shaped how I think about AI, business, cities, and careers."
permalink: /reading/
---
{% comment %} Reading page. The entries come from _data/reading.yml. {% endcomment %}

<ol class="experience-list reading-list">
  {% for item in site.data.reading %}
  <li class="experience-item">
    <p class="reading-type">{{ item.type | escape }}</p>
    <div class="experience-detail">
      <h2><a href="{{ item.url | escape }}" target="_blank" rel="noopener">{{ item.title | escape }}</a></h2>
      {% if item.author and item.author != "" %}
      <p class="reading-author">{{ item.author | escape }}</p>
      {% endif %}
      <p class="experience-summary">{{ item.summary | escape }}</p>
      {% if item.note and item.note != "" %}
      <p class="reading-note"><em>{{ item.note | escape }}</em></p>
      {% endif %}
      {% if item.tags and item.tags.size > 0 %}
      <ul class="tag-list" aria-label="Tags for {{ item.title | escape }}">
        {% for tag in item.tags %}
        <li>{{ tag | escape }}</li>
        {% endfor %}
      </ul>
      {% endif %}
    </div>
  </li>
  {% endfor %}
</ol>

<p>More on my bookshelf at <a href="https://www.goodreads.com/thalhah" target="_blank" rel="noopener">Goodreads</a>.</p>
