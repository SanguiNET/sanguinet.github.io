---
layout: archive
title: "Sample Media Gallery"
date: 2014-05-30T11:40:45-04:00
modified:
excerpt: "Un archivo de adjuntos multimedia de SanguiNET."
tags: []
image:
  feature:
  teaser:
---

<div class="tiles">
{% for post in site.categories.media %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
