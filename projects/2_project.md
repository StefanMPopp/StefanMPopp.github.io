link between the---
layout: page
title: current - more ant search studies
description: following up from my PhD, I am currently conducting 2 more studies; an empirical one on ant search on rugose surfaces and a modeling study on the efficiency of the meanders we described in my first PhD chapter.
img: assets/img/3.jpg
importance: 2
category: research
giscus_comments: false
---

<h4>efficiency of meandering</h4>
In my [PhD work](/projects/1_project/), I described a novel regular fractal-like meandering pattern in searching ants. I showed that it is theoretically more efficient than pure Correlated Random Walks with similar properties, since the ant tracks cross themselves less.
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

<details> 
  <summary>pseudocode </summary>

    {% raw %}

    ```
    pseudocode
    ```
    
    {% endraw %}

</details>


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
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="panel" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="video" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    matlab thing; pic of plates; video
</div>

This study will be important for the translation of results from lab studies into ecological contexts.
