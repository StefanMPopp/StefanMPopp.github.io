---
layout: page
title: resampling
description: method comparison - showing that the choice of resampling (turn ID) method can have large effects on the results of movement ecological studies
img: assets/img/1.jpg
importance: 3
category: research
---
This manuscript was my 4th PhD thesis chapter and is about to be submitted (as of Mar 2024).

When moving, animals may change their direction due to internal or external causes, and these ‘turns’ are of interest in many research areas in animal movement and decision-making. However, even between such ‘deliberate’ turns, measured animal tracks are not generally straight due to navigational, environmental, or tracking ‘noise’, making the distinction between a ‘true’ turn and local noise non-trivial. To identify those biologically significant turns, studies of animal movement use turn identification methods, often based on resampling from original tracks, i.e. reconstituting what is considered the relevant movement track of the animal from a subset of the original measured location points. The accuracy and consistency of such methods have rarely been validated against ground truth trajectories with known 'true' turns and noise.
We analyzed simulated tracks with known parameters as well as some empirical tracks and identify turns with 8 different frequently used resampling methods. We compare the known properties of the paths (e.g. mean turn angle, step length) with the resampled trajectories.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/resamp/fig1.png" title="Methods Overview" class="img-fluid rounded z-depth-1" %}
    </div>
    
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/resamp/tracks_snt.png" title="Step & turn resampled tracks" class="img-fluid rounded z-depth-1" %}
    </div>

    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/resamp/tracks_curvy.png" title="Curvy resampled tracks" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Overview of methods: making tracks, resampling them, comparing ground truth with resampled tracks. <strong>Middle:</strong> Example step-and-turn track and its resampled tracks. <strong>Right:</strong> Curvy track and its resampled tracks.
</div>

We find that most results differ from the ground truth by more than 50%, and vary greatly both between and within methods. Results were also highly sensitive to the chosen resampling threshold (e.g. max angle) of some, but not all methods. Our results demonstrate the large impact of resampling method selection, and the variability of results even within a population of similar trajectories. One should thus be cautious when comparing results between studies using different resampling methods.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/resamp/r1_accVar.png" title="Main result" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/resamp/r3_thresh.png" title="Threshold results" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Large variation in characteristics of resampled tracks. <strong>Right:</strong> 
</div>

