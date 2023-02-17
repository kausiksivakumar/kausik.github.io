---
layout: page
title: Building dynamics models through contact discontinuitites
description: ICRA 2022 conference demo with DAIR lab UPenn
img: assets/img/ICRA2022/dair_franka.png
importance: 4
category: work
---
This demo demonstrates learning object mesh and fricition parameters of a cube by observing its contact rich interactions with the flat table. I worked with Penn PhD student [Mathew Halm](https://matthalm.net/), Penn PhD student [Bibit Bianchini](http://www.bianchini-love.com/bibit) and Penn faculty [Michael Posa](https://www.grasp.upenn.edu/people/michael-posa/). 
<div class="row">
    <iframe style="display: block; margin: auto;" width="560" height="315" src="https://www.youtube.com/embed/Ko9i11to9_A" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
</div>
<div class="caption">
    Video of the ICRA demonstration. 
</div>

The setup is a Franka robot arm that is tasked to toss a cube that is tracked with three point grey cameras. The contactnets model learns the object mesh that is presented via an interactive browser. We see a good prediction of the object mesh in around 20 tosses of the cube. 

The thumbnail and the video used in this page is taken with permission from Bibit Bianchini's project [page](http://www.bianchini-love.com/posts/live-contactnets-demo-with-franka-arm), which further details the implementation of this work.  
