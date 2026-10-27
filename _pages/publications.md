---
layout: page
permalink: /publications/
title: Publications
description: Publications and preprints.
nav: true
order: 2
---
<!-- _pages/publications.md -->
<div class="publications">

<p>
If you're doing research in a similar area, you might find this list of relevant conferences and deadlines helpful: <a href="https://hcorinna.github.io/fair-deadlines/?cat=conference,specialissue&sub=AIE,CSS,DH,NLP,IR,HCI,MD,ML,DM,CV" target="_blank">https://hcorinna.github.io/fair-deadlines/</a>
</p>

<div class="pub-filters" role="group" aria-label="Filter publications by category">
  <button type="button" class="pub-filter active" data-filter="all">All</button>
  {%- for cat in site.data.categories %}
  <button type="button" class="pub-filter cat-{{ cat[0] }}" data-filter="{{ cat[0] }}">{{ cat[1].name }}</button>
  {%- endfor %}
</div>

{% bibliography %}

</div>

<script>
  (function () {
    var buttons = document.querySelectorAll('.pub-filter');
    var entries = document.querySelectorAll('.publications ol.bibliography > li');
    var headings = document.querySelectorAll('.publications h2.bibliography');

    function applyFilter(filter) {
      buttons.forEach(function (b) {
        b.classList.toggle('active', b.dataset.filter === filter);
      });
      entries.forEach(function (li) {
        var row = li.querySelector('[data-category]');
        var cat = row ? row.dataset.category : '';
        li.classList.toggle('hidden-entry', filter !== 'all' && cat !== filter);
      });
      // Hide year headings whose list has no visible entries
      headings.forEach(function (h) {
        var list = h.nextElementSibling;
        while (list && list.tagName !== 'OL') list = list.nextElementSibling;
        var visible = list ? list.querySelectorAll('li:not(.hidden-entry)').length : 0;
        h.classList.toggle('hidden-group', visible === 0);
        if (list) list.style.display = visible === 0 ? 'none' : '';
      });
    }

    buttons.forEach(function (b) {
      b.addEventListener('click', function () {
        var filter = b.dataset.filter;
        if (history.replaceState) {
          history.replaceState(null, '', filter === 'all' ? location.pathname : '#' + filter);
        }
        applyFilter(filter);
      });
    });

    var initial = location.hash.replace('#', '');
    var known = Array.prototype.some.call(buttons, function (b) { return b.dataset.filter === initial; });
    applyFilter(known ? initial : 'all');
  })();
</script>
