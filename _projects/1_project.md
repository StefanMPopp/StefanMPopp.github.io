---
layout: page
title: ant search
description: PhD thesis - Ant search strategies for targets of unkown locations
img: assets/img/publication_preview/mndr_graph.jpg
importance: 1
category: research
related_publications: true
---

These are the first 3 chapters of my PhD thesis

<h3>methods</h3>
I let 5 whole colonies of ants search freely in a custom-built large arena which I recorded with 4 cameras to track the ants' movements. Since I was interested in their search behavior for novel targets, I never added any resources in the arena.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/temno.png" title="Ant" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Nest.jpg" title="artificial nest" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/setup_below.jpg" title="arena" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> The study species, <em>Temnothorax rugatulus</em> (by Takao Sasaki), <strong>Middle:</strong> Artificial nest with colony which was placed in the arena underneath a layer of paper. <strong>Right:</strong> Experimental arena (2x3 m, ~1000x an ant's size).
</div>

<h3>data processing</h3>
I preprocessed the 4 5h long 4K videos with a bash routine, first applying filters in ffmpeg and cutting them up for more accurate tracking ([bash script](https://github.com/StefanMPopp/antSearch_dataProcessing/blob/main/batchffmpeg)). The processed videos were then fully automatically tracked with [TRex](https:\\www.trex.run) ([bash script](https://github.com/StefanMPopp/antSearch_dataProcessing/blob/main/batchTrex)).

For the following data cleaning and annotation, I developed an extensive routine which allowed for semi-automatic aligning and combination of different data sets, outlier exclusion, and tracking error correction. This involved various scripts for the creation of 3D interactive plots with specific functionalities to enable the visual inspection and correction of data. The manual part of the data correction was mainly carried out by undergraduate research assistants which I mentored. The whole data pipeline was thus designed to be user friendly, reproducible, and contained validity checks. I created several tutorials which helped with the training of this complex set of tasks.

<div class="row">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/allTracksT1.png" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include video.liquid path="https://youtu.be/egDTFIUHBgs?si=Fw6ms9JmLctgJiy_" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong>Ant paths from one colony evolving over the 5 h of one trial. <strong>Right:</strong>Tutorial for the joining of erroneously broken up tracks.
</div>

TODO: The things we found: Pics of meandering, explore heatmaps/histograms, and FP heatmap? Meander: {% cite popp_ants_2023 %}
Exploration: {% cite popp_ant_2023 %}
FP to be replaced: {% cite popp_ant_2023 %}
Key results from SICB app, with significance?


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/tr_extreme_F1small.bmp" title="sharkSmall" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
