---
layout: page
title: swarm model
description: showing how a swarm of agents can escape a dead end obstacle
img: assets/img/publication_preview/align_prev.png
importance: 3
category: research
related_publications: true
---

At the MBI [workshop](https://mbi.osu.edu/events/collective-behavior-and-emergent-phenomena-biology) for collective behavior, I forged a collaboration with [Helen McCreery](https://facultyprofiles.tufts.edu/helen-mccreery), [Varun Joshi](https://www.varun-joshi.com/about), and [Justin Werfel](https://people.seas.harvard.edu/~jkwerfel/). We created swarms using a classical model of swarming (agents avoid, align, and get attracted to others in the swarm depending on discrete distance zones around the focal agent) which are on their way to a goal. We showed that these swarms can escape a dead-end obstacle without any additional rules besides being repelled by the obstacle. The escape probability depends mostly on the strength of alignment: The higher this parameter, the more likely it is that swarms either follow the walls or 'bounce' out of the obstacle.
{% cite joshi_alignment_2022 %}

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/swarmFig.jpg" title="swarmFig" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> Illustration of the model, <strong>Middle:</strong> Escape of the swarm, <strong>Right:</strong> Trapped swarm.
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/swarmGif.gif" title="swarmGif" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example of a splitting swarm.
</div>

The code can be found [here](https://github.com/v9joshi/Obstacle-avoiding-agents).
