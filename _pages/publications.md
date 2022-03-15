---
layout: page
permalink: /publications/
title: Publications
description: If you're doing research in a similar area, you might find this list of relevant conferences and deadlines helpful: <a href="https://hcorinna.github.io/fair-deadlines/?sub=AIE,CSS,MD,ML,DM,CV" target="_blank">https://hcorinna.github.io/fair-deadlines/</a>
years_conferences: [2022, 2021]
years_journals: [2022, 2021]
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

<h1>Preprints</h1>
{% bibliography -f preprints %}

</div>
