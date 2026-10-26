---
layout: page
title: ant search
description: PhD thesis - Ant search strategies for targets of unkown locations
img: assets/img/publication_preview/mndr_graph.jpg
importance: 2
category: research
related_publications: true
---

These are the first 3 chapters of my PhD thesis. I continue to work on the topic of ant search in 2 other projects.

How do you search for a small item in a huge space you cannot oversee? Previously, the question of how ants search for unknown resources had barely been addressed in the scientific literature. I created to date the largest arena for tracking ants to describe their search patterns and answer questions about the influences of experience and communication.

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
        {% include figure.liquid loading="eager" path="assets/ant_search/Setup_below.jpg" title="arena" class="img-fluid rounded z-depth-1" %}
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
    <strong>Left:</strong> Ant paths from one colony evolving over the 5 h of one trial. <strong>Right:</strong> Tutorial for the joining of erroneously broken up tracks.
</div>

<h3>results</h3>
<h4>ants meander regularly</h4>
Ants do not merely walk purely randomly, as was previously assumed, but rather meander in regularly alternating smooth turns. This systematic element makes their search patterns more space-filling, and thus efficient, while the randomness conserves flexiblity and robustness to noise and obstacles.
{% cite popp_ants_2023 %}

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/tr_extreme_F1.png" title="sharkSmall" class="img-fluid rounded z-depth-1" %}
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
        {% include figure.liquid path="assets/ant_search/f1_heat.png" title="Heatmap" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/f2_disp.png" title="displacements" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/ant_search/f4b_tracks.png" title="first and last tracks" class="img-fluid rounded z-depth-1" %}
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

#### efficiency of meandering
In my PhD work, I described a novel regular fractal-like meandering pattern in searching ants. I showed that it is theoretically more efficient than pure Correlated Random Walks with similar properties, since the ant tracks cross themselves less.
In this project, I aim to recreate the meandering in a simulation using a plausible mechanism and compare its efficiency for finding targets in noisy environments against other propsed search strategies.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/publication_preview/mndr_graph.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Meandering ant track. The coordinates are in mm.
</div>

The meandering algorithm is based on a recursive function: the agent has a current goal direction, from which it turns away with a constant angular velocity until it is facing a threshold angle away from the goal direction, at which point the agent switches the turn direction. The current goal direction meanders itself around a larger-scale goal direction. The below image of the meander simulation is created with 3 levels of meandering.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/p07.png" title="sim meander" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/lw.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/p14.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Simulated tracks. <strong>Left:</strong> meandering, <strong>Middle:</strong> Levy Walk, <strong>Right:</strong> Spiral
</div>

I will test the target finding efficiency of these strategies in different target environments and with different levels of 'noise' in the movement.

The ultimate goal of this project is, to implement a version of the meandering strategy in search robot swarms, depending on the results of this simulation.



<h4>search on 3D surfaces</h4>
So far, the detailed search behavior of ants has only been investigated either in arenas in the lab, or on completely flat desert surfaces. Most ants in the wild are walking on highly 3-dimensional surfaces. How do ants adapt their search patterns to rugose surfaces? I am collaborating with the Dornhaus lab to answer this question
Ants could conserve more the walk tortuosity from a bird's-eye view (ignoring the structure in the z-axis), or on the surface from an ant's-eye view (ignoring the fact that more surface is now packed in a smaller bird's-eye view area). Other alternatives are possible.

We 3D-printed panels with sinusoidal waves of different frequency which tile the floor of a search arena. We will again record and track ants as they are searching for (nonexistent) resources.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/12.jpg" title="panel" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/ss_tracks.png" title="video" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/12.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    matlab thing; Trajectories in the arena; video?
</div>

This study will be important for the translation of lab results into ecological contexts.
