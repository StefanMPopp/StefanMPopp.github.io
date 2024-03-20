---
layout: page
title: ant search
description: PhD thesis - Ant search strategies for targets of unkown locations
img: assets/img/publication_preview/mndr_graph.jpg
importance: 2
category: research
related_publications: true
---

These are the first 3 chapters of my PhD thesis. I continue to work on the topic of ant search in 2 other [projects](/projects/curr_project/).


<h3>methods</h3>
I let 5 whole colonies of ants search freely in a custom-built large arena which I recorded with 4 cameras to track the ants' movements. Since I was interested in their search behavior for novel targets, I never added any resources in the arena.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/ant_search/temno.png" title="Ant" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/ant_search/Nest.jpg" title="artificial nest" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/ant_search/setup_below.jpg" title="arena" class="img-fluid rounded z-depth-1" %}
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
        {% include figure.liquid path="assets/ant_search/allTracksT1.png" class="img-fluid rounded z-depth-1" controls=true autoplay=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/videoseries?si=DagoqMy98GHEeWVI&amp;list=PLhic1Oo3tm8AdnKNJo9LaKkR5mUw2ZwzA" title="YouTube video player tutorials" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
    </div>
</div>
<div class="caption">
    <strong>Left:</strong>Ant paths from one colony evolving over the 5 h of one trial. <strong>Right:</strong>Tutorial for the joining of erroneously broken up tracks.
</div>

<h3>results</h3>
<h4>ants meander regularly</h4>
Ants do not merely walk purely randomly, as was previously assumed, but rather meander in regularly alternating smooth turns. This systematic element makes their search patterns more space-filling, and thus efficient, while the randomness conserves flexiblity and robustness to noise and obstacles.
{% cite popp_ants_2023 %}

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/tr_extreme_F1small.bmp" title="sharkSmall" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/trShrkfin.png" title="close up meanders" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Track section of a strongly meandering ant. Grid lines are 20 cm apart. <strong>Right:</strong> Close-up example of a meandering track.
</div>

<h4>ants explore more near the nest in a novel environment</h4>
The study species often relocates their nest, requiring the foragers to get familiar with their new environment for effective navigation and search. Over 3 days after being placed into a new arena, ants moved less only near the nest, where movements are slower and curvier. This reflects a shift from familiarization or marking to searching. However, we don't see stereotyped 'learning walks', like in some desert ant species.
{% cite popp_ant_2023 %}

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/f1_heat.png" title="sharkSmall" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/f2_disp.png" title="close up meanders" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/f4b_tracks.png" title="close up meanders" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Heatmaps of all ant locations on the 3 days. <strong>Middle</strong> Histograms of ant locations by nest distance: on subsequent days, i.e., with increasing familiarity of the ants with the arena, there are fewer exploratory movements near the nest <strong>Right:</strong> Tracks from the first 5 min on the first day, vs the last 5 min on the last day. There is no measurable difference in movement patterns, i.e. no special 'learning walks'.
</div>

<h4>ants do not coordinate their search much through chemical signals</h4>
Previous work showed that ants walk straighter and faster on surfaces which are marked with chemical footprints of nestmates. We find the opposite effect, which we explain by a) footprints making ants walk straighter, and b) interindividual variation combined with environmental heterogeneity mean reverse causation to the expected. In nature, environmental cues are likely more important than chemical footprints. 
To be replaced once published: {% cite popp_ant_2023 %}

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/fpHeatVari.png" title="heatmap with variation tracks" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/fpHeatTape.png" title="heatmap with tape" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Heatmap of all ant points on the 3rd day, with an illustration of interindividual variation in path straightness <strong>Right:</strong> Heatmap with illustration of the locations of adhesive tape several layers below the topmost paper.
</div>

<h4>trying to find patterns and recreate tracks using machine learning</h4>
As a side project, I collaborated with the [Kobourov lab](https://profiles.arizona.edu/person/kobourov) and [Alon Efrat](https://www2.cs.arizona.edu/~alon/) to identify and characterize patterns in the movement patterns, like the meanders. We applied dimensionality reduction and clustering,identifying common motifs of the meandering, and explored the creation of tracks via a specialized General Adversarial Network and an ARIMA model

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/eigenantLong.png" title="eigenant" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/movAv.png" title="moving average" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/arima.png" title="arima" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Trajectory created by drawing randomly from the set of identified curve eigenvectors, <strong>Middle:</strong> Empirical ant track with moving average, which could be used to separate the patterns on different scales <strong>Right:</strong> Empirical track segment and ARIMA forecast of it.
</div>

Code can be found [here](https://github.com/ryngray/model_ant_trajectories).
