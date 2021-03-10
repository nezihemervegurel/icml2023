---
layout: page
title: Measures & Metrics
description: Collection of SOTA ML quality assurance methods like bias, generalizations, robustness, uncertainty, and so forth about use cases and regulatory topics.
img: /assets/img/m&m.png
contact: Luis Oala (luis@aiaudit.org) and Pat Baird (pat@aiaudit.org)
coordinates: Every Thursday, 2:00 PM, Geneva Time
importance: 2
worktype: bg-success
lifecyclesteps: 1 2 3 4
github: 
---
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/IMDRF-ICD.png' | relative_url }}" alt="" title="" width="{{ site.max_width }}" height="100"/>
    </div>
</div>
<br/>

# Scope
Since 2020, the Measures & Metrics workstream has researched regulatory aspects inside of Machine Learning for Health. We study a collection of SOTA ML quality assurance methods like bias, generalizations, robustness, uncertainty, and so forth about use cases and regulatory topics. Our expectation is finish the project until the end of 2022.

Today, our multidisciplinary team has students and professionals from different companies, laboratories, universities worldwide focusing on creating regulatory documents and providing better solutions to society.

We already developed a paper about Machine Learning for Health Audit in this workstream (see in publications). Our objective is to move to easy to maintain and use web resources.

#### Aims
Develop better regulations by publications, international standards about measures, and metrics inside Machine Learning for Health.

#### Planned Outputs
* Regulatory documents about measures & metrics inside of Machine Learning.
* Paper about bias, robustness, uncertainties and other aspects of M&M in ML4H.

---
# Collaboration resources
You are welcome to inquire about the work stream and opporunities for collaboration directly with the work stream team.
* **General contact**

#### Meetings
Regular meetings for this work stream take place at the below coordinates. 
* **Meetings** Thursdays, 16.00 hrs, Geneva
* **Zoom room**

#### Communication
You can subsbscribe to the work stream mailing list to receive updates and join the asynchronous group chat.
* **Group chat**
* **Mailing list**

#### Tools
We use different tools in our remote work. They include shared documents, github projects for code as well as task tracking and a collaborative whiteboard for ideation. You can request access via the below links.
* **Shared document**
* **Github project**
* **Collaborative whiteboard** 

You can find more information about the way we usually carry out our work remotely in teams [here](https://aiaudit.org/join).

---

# Milestones

<div class="news">
  {% if site.news  %}
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {% assign news = site.news | reverse %}
      {% for item in news limit: site.news_limit %}
        <tr>
          <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
          <td>
            {% if item.inline %}
              {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {% else %}
              <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {% endif %}
          </td>
        </tr>
      {% endfor %}
      </table>
    </div>
  {% else %}
    
  {% endif %}
</div>
TODO: news filtered with project slug

# Related work and resources
This is a list of related work and resources relevant for this work stream.
TODO: ref with tag
