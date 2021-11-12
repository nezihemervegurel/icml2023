---
layout: about
title: about
permalink: /
description: We are a group of humans who audit AI systems.

profile:
  align: #right
  image: #prof_pic.jpg

news: true  # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---

{% include visual.html %}


Modern AI systems based on deep learning, reinforcement learning or hybrids thereof constitute a flexible, complex and often opaque technology. Limits in our understanding of an AI system’s behavior constitute risks for system failure. Hence, the identification of failure modes in AI systems is an important pre-requisite for their reliable deployment to real-world settings.

*aiaudit.org* is a [cooperative of humans](https://aiaudit.org/contributors/) working at the intersection of machine learning research, regulation, software development and application domains. We design methods, processes and standardization contributing towards AI technology that can be trusted for use in real-world applications. 
<!-- For that purpose, many of us contribute their expertise to standardization efforts such as the [ITU/WHO Focus Group on Artificial Intelligence for Health](https://www.itu.int/en/ITU-T/focusgroups/ai4h/Pages/default.aspx) or [Xavier AI Team](https://www.xavierhealth.org/news3/2020/11/11) of the FDA's Digital Health Center of Excellence. -->

This site is the group's interface to present and organize its work. We maintain information on current projects below. We are committed to equitable collaboration. Project groups form in a self-organized way and are open to interested persons from research, companies, the general public or otherwise.

## Core activities

<div class="projects grid">

  {% assign sorted_contributors = site.coreprojects | sort: "importance" %}
  {% for contributor in sorted_contributors %}
  <div class="grid-item">
    {% if contributor.redirect %}
    <a href="{{ contributor.redirect }}" target="_blank">
    {% else %}
    <a href="{{ contributor.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if contributor.img %}
        <img src="{{ contributor.img | relative_url }}" alt="contributor thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title">{{ contributor.name }}</h2>
          <!-- <p class="card-title">{{ contributor.affiliation }}</p> -->
          <p class="card-text">{{ contributor.minibio }}</p>
          <br/>
          <div class="row ml-1 mr-1 p-0">
            {% if contributor.mail %}
            <div class="col-sm-2">
              <div class="icon" data-toggle="tooltip" title="Email">
                <a href="mailto:{{ contributor.mail | encode_email }}"><i class="fas fa-envelope"></i></a>
              </div>
            </div>
            {% endif %}
            {% if contributor.website %}
            <div class="col-sm-2">
              <div class="icon" data-toggle="tooltip" title="Website">
                <a href="{{ contributor.website }}" target="_blank"><i class="fas fa-globe"></i></a>
              </div>
            </div>
            {% endif %}
            {% if contributor.twitter %}
            <div class="col-sm-2">
              <div class="icon" data-toggle="tooltip" title="Twitter">
                <a href="{{ contributor.twitter }}" target="_blank"><i class="fab fa-twitter"></i></a>
              </div>
            </div>
            {% endif %}
            {% if contributor.linkedin %}
            <div class="col-sm-2">
              <div class="icon" data-toggle="tooltip" title="LinkedIn">
                <a href="{{ contributor.linkedin }}" target="_blank" title="LinkedIn"><i class="fab fa-linkedin"></i></a>
              </div>
            </div>
            {% endif %}
            {% if contributor.googlescholar %}
            <div class="col-sm-2">
              <div class="icon" data-toggle="tooltip" title="Google Scholar">
                <a href="{{ contributor.googlescholar }}" target="_blank" title="Google Scholar"><i class="ai ai-google-scholar"></i></a>
              </div>
            </div>
            {% endif %}
            {% if contributor.github %}
            <div class="col-sm-2">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ contributor.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if contributor.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ contributor.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>


{% if page.news %}
  {% include news.html %}
{% endif %}
