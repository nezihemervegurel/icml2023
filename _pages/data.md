---
layout: distill
permalink: /lens2logit/data/
title: From Lens to Logit
description: Data
nav: false
nav-order: b
date: 2021-08-27

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
**Data** [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5235536.svg)](https://doi.org/10.5281/zenodo.5235536) 
<!---<d-cite key="gregor2015draw"></d-cite>--->

*This page contains information on the data used in the manuscript ["From Lens to Logit: Addressing Camera Hardware-Drift Using Raw Sensor Data"](https://openreview.net/forum?id=DRAywM1BhU), submitted to the NeurIPS 2021 Datasets and Benchmarks Track. You can find more information on the [project page](https://aiaudit.org/lens2logit/)*

Within the Lens2Logit framework, we make available two datasets: **Raw-Microscopy** and **Raw-Drone**

## Raw-Microscopy
The dataset Raw-Microscopy contains:
* **940 raw bright-field microscopy images** of human blood smear slides for leukocyte classification (microscopy/images/raw_scale100) with corresponding labels (microscopy/labels).
* **5,640 variations** measured at **six** additional **different intensities** (microscopy/images/raw_scale001-raw_scale0075)
* **11,280 images of the raw sensor data processed through twelve different pipelines** (microscopy/images/processed_views)
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
### Data acquisition
Assessment of blood smears under a light microscope is a key diagnostic technique <d-cite key="Bain2005"></d-cite>. The creation of image datasets and machnine learning models on them has received wide interest in recent years <d-cite key="Scotti2011"></d-cite><d-cite key="Matek2019"></d-cite><d-cite key="Ayyappan2020"></d-cite>. Here, we use a bright-field microscope to image blood smear cytopathology samples. The light source is a halogen lamp equipped with a 0.55 NA condenser, and a pre-centred field diaphragm unit. We use filters at 450 nm, 525 nm and 620 nm to acquire the blue, green and red channels respectively. The condenser is followed by a 40 $$\times$$ objective with 0.95 NA (Olympus UPLXAPO40X). Slides can be moved via a piezo with 1 nm spatial resolution, in the three directions. We focus by maximizing the variance of the pixel values. Images are acquired is 16 bit, with a 2560 $$\times$$ 2160 pixels CMOS sensor (PCO edge 5.5). We measured the PSF to be 450 nm with 100 nm nanospheres. Mechanical drift was measured at 0.4 pixels per hour. Imaging was performed on de-identified human blood smear slides (Ma190c Lieder, J. Lieder GmbH & Co. KG, Ludwigsburg/Germany). All slides were taken from healthy humans without known hematologic pathology. Imaging regions were selected to contain single leukoytes in order to allow unique labelling of image patches, and regions were cropped to 256 $$\times$$ 256 pixels. All images were annotated by a trained hematological cytologist using the standard scheme of normal leukocytes comprising band and segmented neutrophils, typical and atypical lymphocytes, monocytes, eosinophils and basophils <d-cite key="longanbach2016rodak"></d-cite>. To soften class imbalance, candidates for rare normal leukocyte types were preferentially imaged, and enrich rare classes. Additionally, two classes for debris and smudge cells, as well as cells of unclear morphology were included. Labelling took place for all imaged cells from a particular smear at a time, with single-cell patches shown in random order. RI are generated using JetRaw Data Suite features. Blue, red and green channels are metrologically rescaled independently in intensity to simulate a standard RGB camera condition. From each channel, some pixels are discarded complementary on each channel in order to obtain a Bayer filter pattern.
### Labels
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/Microscopy_classes.png" data-zoomable>
    </div>
</div>
<div class="caption">
     Samples from each class in the Raw-Microscopy dataset.
</div>

### Intensity levels
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/DifferentIntensities.png" data-zoomable>
    </div>
</div>
<div class="caption">
     Raw data at different intensity levels.
</div>

### Static processed variations
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/ABpipelines_Microscopy.png" data-zoomable>
    </div>
</div>
<div class="caption">
    Static processing variations on the Raw Microscopy dataset.
</div>

## Raw-Drone
The dataset Raw-Drone contains:
* **548 raw drone camera images** for car segmentation (drone/images_tiles_256/raw_scale100) with corresponding binary segmentation mask (drone/masks_tiles_256). The images and the masks are cropped from 12 raw drone camera images (drone/images_full/raw_scale100) and 12 masks (drone/masks_full) of size 3648 by 5472.
* **3,288 variations** measured at **six** additional **different intensities** (drone/images_tiles_256/raw_scale001-raw_scale075).
* **6,576 images of the raw sensor data processed through twelve different pipelines** (drone/images_tiles_256/processed_views)
| Tables        | Are           | Cool  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
### Data acquisition
We used a DJI Mavic 2 Pro Drone, equipped with a Hasselblad L1D-20c camera (Sony IMX183 sensor) having 2.4 $\micro$m pixels in Bayer filter array. The objective has a focal length of 10.3 mm. We set the f-number $$N=8$$, to emulate the PSF circle diameter relative to the pixel pitch and ground sampling distance (GSD) as would be found on images from high-resolution satellites. The point-spread function (PSF) was measured to have a circle diameter of 12.5$\micro$m. This corresponds to a diffraction-limited system, within the uncertainty dominated by the wavelength spread of the image. Images were taken at 200 ISO, a gain of 0.528 DN/$e^-$. The 12-bit pixel values are however left-justified to 16-bits, so that the gain on the 16-bit numbers is 8.448 DN/$e^-$. The images were taken at a height of 250 m, so that the GSD is 6 cm. All images were tiled in 256  $$\times$$ 256 patches. Segmentation color masks were created to identify cars for each patch. From this mask, classification labels were generated to detect if there is a car in the image. The dataset is constituted by 548 images for the segmentation task, and 930 for classification. The dataset is augmented through JetRaw Data Suite, with 7 different intensity scales.
### Labels
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/Drone_masks.png" data-zoomable>
    </div>
</div>
<div class="caption">
     Samples of masks in the Raw-Drone dataset.
</div>

<!---### Intensity levels--->
### Static processed variations
<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ site.baseurl }}/assets/img/lens2logit/ABpipelines_Drone.png" data-zoomable>
    </div>
</div>
<div class="caption">
     Static processing variations on the Raw Drone dataset.
</div>

## Access
If you use our code you can use the convenient cloud storage integration. Data will be loaded automatically.
We also maintain a copy of the entire dataset with a persistent and permanent identifier at Zenodo which you can find under identifier [10.5281/zenodo.5235536](https://doi.org/10.5281/zenodo.5235536).
## License
The data is published under a [Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) which allows liberal copying, redistribution, remixing and transformation.
The authors bear all responsibility for the published data.
 
