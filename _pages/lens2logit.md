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

bibliography: lens2logit.bib

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
<!---[**Interactive experiment browser**](http://deplo-mlflo-1ssxo94f973sj-890390d809901dbf.elb.eu-central-1.amazonaws.com/#/)--->
<!---<d-cite key="gregor2015draw"></d-cite>--->
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/pmflow8.png" data-zoomable>
    </div>
</div>
To create an image, raw sensor data traverses complex image signal processing pipelines. These pipelines are used by cameras and scientific instruments to produce the images fed into machine learning systems. The processing pipelines vary by device, influencing the resulting image statistics and ultimately contributing to what is known as hardware-drift. However, this processing is rarely considered in machine learning modelling, because available benchmark data sets are generally not in raw format. Here we show that pairing qualified raw sensor data with an explicit, differentiable model of the image processing pipeline allows to tackle camera hardware-drift. Specifically, we demonstrate (1) the controlled synthesis of hardware-drift test cases, (2) modular hardware-drift forensics, as well as (3) image processing customization. We make available two data sets. The first, Raw-Microscopy, contains 940 raw bright-field microscopy images of human blood smear slides for leukocyte classification alongside 5,640 variations measured at six different intensities and twelve additional sets totalling 11,280 images of the raw sensor data processed through different pipelines. The second, Raw-Drone, contains 548 raw drone camera images for car segmentation, alongside 3,288 variations measured at six different intensities and also twelve additional sets totalling 6,576 images of the raw sensor data processed through different pipelines.
<!---## Methods--->
## Raw data
### Raw Microscopy
Assessment of blood smears under a light microscope is a key diagnostic technique <d-cite key="Bain2005"></d-cite>. The creation of image datasets and machnine learning models on them has received wide interest in recent years <d-cite key="Scotti2011"></d-cite><d-cite key="Matek2019"></d-cite><d-cite key="Ayyappan2020"></d-cite>. Here, we use a bright-field microscope to image blood smear cytopathology samples. The light source is a halogen lamp equipped with a 0.55 NA condenser, and a pre-centred field diaphragm unit. We use filters at 450 nm, 525 nm and 620 nm to acquire the blue, green and red channels respectively. The condenser is followed by a 40 $$\times$$ objective with 0.95 NA (Olympus UPLXAPO40X). Slides can be moved via a piezo with 1 nm spatial resolution, in the three directions. We focus by maximizing the variance of the pixel values. Images are acquired is 16 bit, with a 2560 $$\times$$ 2160 pixels CMOS sensor (PCO edge 5.5). We measured the PSF to be 450 nm with 100 nm nanospheres. Mechanical drift was measured at 0.4 pixels per hour. Imaging was performed on de-identified human blood smear slides (Ma190c Lieder, J. Lieder GmbH & Co. KG, Ludwigsburg/Germany). All slides were taken from healthy humans without known hematologic pathology. Imaging regions were selected to contain single leukoytes in order to allow unique labelling of image patches, and regions were cropped to 256 $$\times$$ 256 pixels. All images were annotated by a trained hematological cytologist using the standard scheme of normal leukocytes comprising band and segmented neutrophils, typical and atypical lymphocytes, monocytes, eosinophils and basophils <d-cite key="longanbach2016rodak"></d-cite>. To soften class imbalance, candidates for rare normal leukocyte types were preferentially imaged, and enrich rare classes. Additionally, two classes for debris and smudge cells, as well as cells of unclear morphology were included. Labelling took place for all imaged cells from a particular smear at a time, with single-cell patches shown in random order. RI are generated using JetRaw Data Suite features. Blue, red and green channels are metrologically rescaled independently in intensity to simulate a standard RGB camera condition. From each channel, some pixels are discarded complementary on each channel in order to obtain a Bayer filter pattern.
### Raw Drone
We used a DJI Mavic 2 Pro Drone, equipped with a Hasselblad L1D-20c camera (Sony IMX183 sensor) having 2.4 $\micro$m pixels in Bayer filter array. The objective has a focal length of 10.3 mm. We set the f-number $$N=8$$, to emulate the PSF circle diameter relative to the pixel pitch and ground sampling distance (GSD) as would be found on images from high-resolution satellites. The point-spread function (PSF) was measured to have a circle diameter of 12.5$\micro$m. This corresponds to a diffraction-limited system, within the uncertainty dominated by the wavelength spread of the image. Images were taken at 200 ISO, a gain of 0.528 DN/$e^-$. The 12-bit pixel values are however left-justified to 16-bits, so that the gain on the 16-bit numbers is 8.448 DN/$e^-$. The images were taken at a height of 250 m, so that the GSD is 6 cm. All images were tiled in 256  $$\times$$ 256 patches. Segmentation color masks were created to identify cars for each patch. From this mask, classification labels were generated to detect if there is a car in the image. The dataset is constituted by 548 images for the segmentation task, and 930 for classification. The dataset is augmented through JetRaw Data Suite, with 7 different intensity scales. 

## Applications
### Controlled synthesis of hardware-drift test cases
The static processing pipeline allows us to generate different views of the same dataset for hardware-drift testing. We evaluate the performance of two task models under twelve different image processing configurations:
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/ABpipelines_Microscopy.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Static processing variations on the Raw Microscopy dataset.
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/ABpipelines_Drone.png" data-zoomable>
    </div>
</div>
<div class="caption">
     Static processing variations on the Raw Drone dataset.
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/1.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Cross-validation results are provided for both blood smears and drone datasets for 12 different processing pipelines. Each point is the average metrics value, with its standard deviation, over 5 k-fold dataset splitting. (Left) Models trained on a selected image processing configuration are evaluated on a different pipeline.  To understand critical hardware-shift drops, metrics values need to be compared with reference values on the diagonal where the model is trained and tested on the same pipeline. For the microscopy case we have a drop in performance for one particular configuration (ma,s,me) while in the drone case there is a more heterogeneous pattern. (Right) Models trained on different processing pipelines are evaluated with with common corruptions benchmark at severity 3. Similar results are obtained for different hardware-shift configurations.
</div>

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/1_1.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Worst case train/test pipelines are compared. In both cases, our model leaked in performances with small changes on RGB channels. (Top) For the blood smears dataset, train/test pipeline shown are respectively me, u, me and ma, s, ga. We measured a 33% metrics (IoU/Accuracy) drop respect to the training pipeline. (Bottom) For the drone dataset, the model has been trained with ma, s, ga and tested with bi, u, me giving an average 20% drop. 
</div>

### Hardware-drift forensics
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/2.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Attained accuracy on the test set after 20 epochs of adversarial optimization of the processing pipeline for varying regularization weight parameter $\lambda$. 
    The individual plots depict the various pipeline parameter selections.
</div>
### Image processing customization
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/3.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Low intensity images processed by a static and a learned pipeline. The plots in the rightmost column display the mean of validation metrics over five cross validation runs. Error bars are reported as one standard deviation. Optimization step 1439 and 915 correspond to epoch 60 into training.
</div>
## Resources
### Data
#### Access
If you use our code you can use the convenient cloud storage integration. Data will be loaded automatically.
We also maintain a copy of the entire dataset with a persistent and permanent identifier at Zenodo which you can find under identifier 10.5281/zenodo.5235536
#### License
The data is published under a [Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) which allows liberal copying, redistribution, remixing and transformation.
The authors bear all responsibility for the published data.
### Code
#### Access
All code is available at the [lens2logit repository](https://github.com/aiaudit-org/lens2logit).
#### License
The code is published under [MIT license](https://choosealicense.com/licenses/mit/) which permits broad commercial use, distribution, modification and private use.
### Virtual lab log
We maintain a collaborative virtual lab log at [this address](http://deplo-mlflo-1ssxo94f973sj-890390d809901dbf.elb.eu-central-1.amazonaws.com/#/). There you can browse experiment runs, analyze results through SQL queries and download trained processing and task models.

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/mlflow.png" data-zoomable>
    </div>
</div>
