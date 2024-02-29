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
I let whole colonies of ants search freely in a custom-built large arena which I recorded with 4 cameras to track the ants' movements. Since I was interested in their search behavior for novel targets, I never added any resources in the arena.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/temno.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Nest.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/setup_below.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    <strong>Left:</strong> The study species, <em>Temnothorax rugatulus</em> (by Takao Sasaki), <strong>Middle:</strong> Artificial nest with colony which was placed in the arena underneath a layer of paper. <strong>Right:</strong> Experimental arena (2x3 m, ~1000x an ant's size).
</div>

<h3>analysis</h3>
I preprocessed the 4 5h long 4K videos with a bash routine, first applying filters in ffmpeg and cutting them up for more accurate tracking. The processed videos were then fully automatically tracked with [TRex](https:\\www.trex.run).

<details><summary>ffmpeg pipeline</summary>

```
code should be here
```

</details>

```
    #!/bin/bash
    dir="/home/stefan/Desktop/2020_clone" # highest common diectory path of input & output of videos
    dirIn='/HRM_V' # input path starting from dir
    dirOut='/allVids' # output path starting from dir
    
    vid="$1" # e.g. T1
    cam="$2" # e.g. NE
    st="$3" # start time in s, e.g. 12

    # run the command <name of this file> vid cam st
    # Example: ffmpegScript T1 NE 12
    
    #######################################################
    #                      Explanation                    #
    # -ss start time                                      #
    # -t  end time                                        #
    # -an sound not exported                              #
    # -vf video filter (increasing contrast & brigthness) #
    # -b  output bitrate                                  #
    #######################################################
    
    #ffmpeg -ss 0:00:${st} -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}01.MP4 &&
    #ffmpeg -ss 0:30:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}02.MP4 &&
    #ffmpeg -ss 1:00:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}03.MP4 &&
    #ffmpeg -ss 1:30:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}04.MP4 &&
    #ffmpeg -ss 2:00:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}05.MP4 &&
    #ffmpeg -ss 2:30:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}06.MP4 &&
    #ffmpeg -ss 3:00:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}1.MP4 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}07.MP4 &&
    #ffmpeg -i ${dir}${dirIn}/HRM_${vid}_${cam}2.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}08.MP4 &&
    #ffmpeg -ss 0:30:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}2.MP4 -t 0:30:02 -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}09.MP4 &&
    #ffmpeg -ss 1:00:00 -i ${dir}${dirIn}/HRM_${vid}_${cam}2.MP4 -t 0:30:${st} -an -vf eq=contrast=2.6:brightness=0.5 -b:v 4M ${dir}${dirOut}/HRM_${vid}_${cam}10.MP4
```

TRex pipeline
```
#!/bin/bash
#dir="/media/stefan/HRM"
dir="/home/stefan/Desktop/2020_clone"
vid="$1" # e.g. T1
cam="$2" # e.g. SW
exp="HRM"

echo "${col} " > ~/Desktop/progress # Writes current computing progress into a text file
for pt in 01 02 03 04 05 06 07 08 09 10
do
 tic=$SECONDS
 tgrabs -i ${dir}/allVids/${exp}_${vid}_${cam}${pt}.MP4 -s ${dir}/trex/tgrabs${cam}.settings -d $dir/tGrabOut &&
 trex -i ${dir}/tGrabOut/${exp}_${vid}_${cam}${pt}.pv -s ${dir}/trex/trex${cam}.settings -d ${dir}/tracks -fishdata_dir ${exp}_${vid}_rawIndiv
 toc=$(($SECONDS - tic)) # Computation time
 echo "${cam}${pt} in ${toc}s" >> ~/Desktop/progress # Writes computing time to progress file for computing time estimation.
done

find ${dir}/tracks -name "*.csv" -type 'f' -size 63c -delete # deletes empty files (<63 bytes)

framesListPath=${dir}/allVids/${exp}_${vid}_framesList.txt
if test -f "$framesListPath"; then
    if test -f "${exp}_${vid}_rawIndiv"; then
        mv ${framesListPath} ${dir}/tracks/${exp}_${vid}_rawIndiv # Moves file with frame #s per video chunk to the folder w/ the current tracks. Needed for track concatenation in MATLAB tr1CatStitch 
    fi
fi
```

TODO: I made a whole MATLAB program w/ tutorials for undergrads `tutorial video`

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

TODO: The things we found, wtih `citations` {% cite popp_ants_2023 %}.{% cite popp_ant_2023 %}, {% cite popp_ant_2023 %}
Key results, with significance

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
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
