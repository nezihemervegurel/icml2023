---
layout: distill
permalink: /lens2logit/
title: From Lens to Logit
description: Addressing Camera Hardware-Drift Using Raw Sensor Data
nav: false
nav-order: b
date: 2021-08-27

authors:
  - name: Luis Oala
    url: "https://luisoala.net/"
    affiliations:
      name: Fraunhofer HHI
  - name: Marco Aversa
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: University of Glasgow
  - name: Kurt Willis
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: Fraunhofer HHI
  - name: Gabriel Nobis
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: Fraunhofer HHI
  - name: Yoan Neuenschwander
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: HEPIA/HES-SO
  - name: Michèle Buck
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: Klinikum rechts der Isar
  - name: Christian Matek
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: Helmholtz Zentrum Munich
  - name: Jérôme Extermann
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: HEPIA/HES-SO
  - name: Enrico Pomarico
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: HEPIA/HES-SO
  - name: Roderick Murray-Smith
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: University of Glasgow
  - name: Christoph Clausen
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: Dotphoton AG
  - name: Bruno Sanguinetti
    url: "https://aiaudit.org/lens2logit/"
    affiliations:
      name: Dotphoton AG

bibliography: 2018-12-22-distill.bib

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }

---
<!---[**Code**](https://github.com/aiaudit-org/lens2logit)--->
<!---[**Data**](https://github.com/aiaudit-org/lens2logit/blob/master/utils/base.py)--->
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/pmflow8.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Scheme of the imaging pipeline, from the sample **x** to the result of a machine learning (ML) task. The measurement process yields metrologically accurate raw data, where the errors on each pixel are uncorrelated and unbiased. This data undergoes Image Signal Processing (ISP) before being used in an ML pipeline. The gradient flows all the way back to this raw data. The measurement process is modeled to simulate different measurement conditions, such as lower illumination. We demonstrate this pipeline in three applications: (1) to synthesize drift test-cases, (2) to study the effect of drift on the specific ML task, and (3) to optimize image processing to the task.
</div>
<!---# Applications
##
##
##
--->
## Data
### Access
If you use our code you can use the convenient cloud storage integration. Data will be loaded automatically.
We also maintain a copy of the entire dataset with a persistent and permanent identifier at Zenodo which you can find under identifier 10.5281/zenodo.5235536
### License
The data is published under a [Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) which allows liberal copying, redistribution, remixing and transformation.
The authors bear all responsibility for the published data.
## Code
### Access
All code is available at the [lens2logit repository](https://github.com/aiaudit-org/lens2logit).
### License
The code is published under [MIT license](https://choosealicense.com/licenses/mit/) which permits broad commercial use, distribution, modification and private use.
