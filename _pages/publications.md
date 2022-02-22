---
layout: page
permalink: /publications/
title: Publications
description: Publications and preprints.
years: [2021, 2022]
nav: true
order: 2
---
<!-- _pages/publications.md -->
<div class="publications">

<h1>Conferences</h1>
{% for y in page.years_conferences %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f conferences -q @*[year={{y}}]* %}
{% endfor %}

<h1>Journals</h1>
{% for y in page.years_journals %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f journals -q @*[year={{y}}]* %}
{% endfor %}
</div>
