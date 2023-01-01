---
layout: page
title: Stacking with Franka robot arm
description: Pick and stacking both static and dynamic blocks using a Franka robot arm
# img:
importance: 5
category: work
github: https://github.com/kausiksivakumar/pick_and_place_with_Franka
---
The project aims to use a Franka arm to pick and stack cubic blocks. Dynamic blocks are provided in a circular table that rotates at a constant rpm. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MEAM520/static_pick.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MEAM520/dynamic_pick.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left - Franka arm picking a static block. Right - Franka arm picking a dynamic block. 
</div>

The code is provided [here](https://github.com/kausiksivakumar/pick_and_place_with_Franka)

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MEAM520/stack_blocks.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Picture of the actual environment stacked static blocks (Dynamic blocks are at the circular table)
</div>