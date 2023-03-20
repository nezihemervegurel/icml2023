---
layout: about
title: about
permalink: /
description: Data-centric Machine Learning Research (DMLR) Workshop at ICML 2023

profile:
  align: #right
  image: #prof_pic.jpg

news: true  # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---

{% include visual.html %}


{% if page.news %}
  {% include news.html %}
{% endif %}

{% twitter https://twitter.com/icmlconf maxwidth=1000 limit=5 %}
