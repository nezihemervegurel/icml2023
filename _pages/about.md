---
layout: about
title: about
permalink: /
description: We are a group of humans who audit AI systems.

profile:
  align: #right
  image: #prof_pic.jpg

news: true  # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---

{% include visual.html %}


Modern AI systems based on deep learning, reinforcement learning or hybrids thereof constitute a flexible, complex and often opaque technology. Limits in our understanding of an AI system’s behavior constitute risks for system failure. Hence, the identification of failure modes in AI systems is an important pre-requisite for their reliable deployment to real-world settings.

*aiaudit.org* is a [cooperative of humans](https://aiaudit.org/contributors/) working at the intersection of machine learning research, regulation, software development and application domains. We [design methods, processes and standardization](https://aiaudit.org/outputs/) contributing towards AI technology that can be trusted for use in real-world applications. For that purpose, many of us contribute their expertise to standardization efforts such as the [ITU/WHO Focus Group on Artificial Intelligence for Health](https://www.itu.int/en/ITU-T/focusgroups/ai4h/Pages/default.aspx) or [Xavier AI Team](https://www.xavierhealth.org/news3/2020/11/11) of the FDA's Digital Health Center of Excellence.

This site is the group's interface to present and organize its work. We maintain information on current projects and their coordinates [on the project sites](https://aiaudit.org/workstreams/). We invite you to take a look. If you are interested to contribute or learn more about our modus operandi please [consult the join page](https://aiaudit.org/join/). We are committed to equitable collaboration. Project groups form in a self-organized way and are open to interested persons from research, companies, the general public or otherwise.

{% if page.news %}
  {% include news.html %}
{% endif %}


<iframe src="https://calendar.google.com/calendar/embed?src=aiauditp2p%40gmail.com&ctz=Europe%2FBerlin" style="border: 0" width="800" height="600" frameborder="0" scrolling="no"></iframe>
