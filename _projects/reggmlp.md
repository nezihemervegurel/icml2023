---
layout: page
title: ML4H Regulatory Good Machine Learning Practices #a project title as it will appear on the website
img: /assets/img/Reg_GP.png #thumbnail logo for the project overview
img2: /assets/img/AIMDSCOPE.png #a second banner for the second half of the page, contents of this banner should be related to the work stream
worktype: bg-primary #select one of the colors (researchandmethods: bg-success, standardizationandregulation: bg-primary, softwaretooling: bg-info)
lifecyclesteps: 1 2 3 #select one or more of the numbers for the life cycle steps 1 2 3 4
description: A set of good machine learning practice guidelines intended to educate the developers and manufacturers of healthcare AI solutions to ensure regulatory compliance for the AI based Medical Devices. #a very short description of
projecttag: reggmlp #use this tag as the name for your project .bib file
contact: Christian Johner, christian.johner@johner-institut.de / Pradeep Balachandran, pradeep@aiaudit.org #Firstname Lastname, email of the general contact
coordinates: Bi-weekly Tuesday, 2:00 PM, CET #Interval and day, HH:MM PM, time zone
zoomroom: https://zoom.us/j/97186065542?pwd=MG9JeUpMYTYzNnhzb0FqMFloc2p2QT09 #link to the zoom room that is used for meetings
groupchat: https://daisamregulat-yxd5890.slack.com #invite/access request link to the group chat
mailinglist: #email of the mailing list that people can subscribe to for this workstream
github: #provide a github link for the project if it exists
whiteboard: #link to the miro whiteboard that is used for the work stream
drive: #link to the shared drive of the work stream (for documents etc)
importance: 2
---
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ page.img | relative_url }}" alt="" title="" width="{{ site.max_width }}" height="100"/>
    </div>
</div>
<br/>

# Scope
This project aims at the development of good machine learning practice guidelines to educate the developers and manufacturers of healthcare AI solutions on how to conduct a comprehensive requirements analysis and conformity assessment procedures for continual product improvement in an iterative and adaptive manner in conformance with the applicable standards and regulations.

#### Aims
* To help manufacturers familiarize with international laws and regulations that applies to AI/ML-based medical devices and to bring them to market quickly and effectively.

* To help internal and external auditors test the legal conformity of AI/ML-based medical devices and the associated life-cycle process

#### Outputs
<div class="publications">
  {% bibliography -f {{ page.projecttag }} -q @*[projectoutput=true]* %}
</div>

---
# Collaboration resources
You are welcome to inquire about the work stream and opporunities for collaboration directly with the work stream team.
* **General contact** {{ page.contact }}

#### Meetings
Regular meetings for this work stream take place at the below coordinates. 
* **Meetings** {{ page.coordinates }}
* **Zoom room** [Click here to join meeting]({{ page.zoomroom }})

#### Communication
You can subsbscribe to the work stream mailing list to receive updates and join the asynchronous group chat.
* **Group chat** [{{ page.groupchat }}]({{ page.groupchat }})
* **Mailing list** {{ page.mailinglist }}

#### Tools
We use different tools in our remote work. They include shared documents, github projects for code as well as task tracking and a collaborative whiteboard for ideation. You can request access via the below links.
* **Shared drive** {{ page.drive }}
* **Github project** {{ page.github }}
* **Collaborative whiteboard** {{ page.whiteboard }}

You can find more information about the way we usually carry out our work remotely in teams [here](https://aiaudit.org/join).

---

# Milestones
<div class="news">
  {% if site.news  %}
    <div class="table-responsive">
      <table class="table table-sm table-borderless">
      {% assign news = site.news | reverse %}
      {% for item in news limit: site.news_limit %}
        {% if item.projecttag == page.projecttag %}
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
        {% endif %}
      {% endfor %}
      </table>
    </div>
  {% else %}
    
  {% endif %}
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ page.img2 | relative_url }}" alt="" title="" width="{{ site.max_width }}" height="100"/>
    </div>
</div>
<br/>

# Important reference material
This is a list of related work and resources relevant for this work stream. It comprises resources the work stream contributors consider good practice.

<div class="publications">
  {% bibliography -f {{ page.projecttag }} %}
</div>


