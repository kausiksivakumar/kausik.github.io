---
layout: page
title: Adaptive Planning with Model Predictive Control (MPC)
description: An adaptive planning approach for avoiding static and dynamic obstacles for autonomous racing
img: assets/img/F1tenth/thumbnail.png
# redirect: https://unsplash.com
importance: 4
category: work
github: https://github.com/kausiksivakumar/f1Tenth_project_final
---

This project is built on an autonomous racecar that is one-tenth the scale of an [F1 vehicle](https://f1tenth.org/). The car utilizes a Hokuyo planar LIDAR sensor to obtain information about the environment. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/F1tenth/car.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Picture of the car (Source - https://f1tenth.org/build.html)
</div>

The project proposes a practical method for map based autonomous racing that avoids both static and dynamic obstacles. We use off the shelf [SLAM](http://wiki.ros.org/hector_slam) algorithm with [TUM raceline optimization](https://github.com/TUMFTM/global_racetrajectory_optimization) to determine the optimal raceline. We generate dynamically feasible trajectories and utilize an MPC to determine the best switching maneuver that avoids obstacles while making maximal progress with respect to the optimal raceline
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/F1tenth/raceline.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Raceline picture from ROS2 Gazebo simulator. Green - optimal raceline & Blue - ego vehicle. 
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/F1tenth/no_obs.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/F1tenth/obstacle.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left - obstacle free navigation. Right - obstacle avoidance
</div>
The algorithm generates dynamically feasible (imagined) trajectories (blue) and chooses one that makes maximal progress (yellow). When the ego vehicle encounters an obstacle (orange), it chooses the best possible alternative (yellow).

The code is provided [here](https://github.com/kausiksivakumar/f1Tenth_project_final)