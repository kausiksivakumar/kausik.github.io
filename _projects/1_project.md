---
layout: page
title: Safe RL using Adaptive Penalty 
description: Unofficial implementation of the paper - "Conservative and Adaptive Penalty for Model-Based Safe Reinforcement Learning" by Ma et. al.
img: assets/img/safety-gym-cover.png
importance: 1
category: work
github: https://github.com/kausiksivakumar/safe_reinforcement_learning
---

This project explores the model-based safe RL approach [CAP](https://arxiv.org/abs/2112.07701). We formulate the safe RL problem as a constrained Markov Decision process and separately optimise over cost and rewards. CAP adaptively controls the penalty that encourages exploratory behavior with increase in environmental interactions. Our contribution is integrating CAP with [Safety GYM](https://openai.com/blog/safety-gym/) environment and introducing a novel optimized gradient approach for policy learning. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE650_CAP/PointGoal.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example of the environment: The agent (red) aims to reach the goal position (green) while avoiding unsafe regions (light and dark blue).
</div>
With our experiments we notice lower cost-violations on the point-mass safety-GYM environment. 
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE650_CAP/EpCost.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE650_CAP/EpRet.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: Episodic cost (less   => better). Right: Episodic return (more => better)
</div>


The code as well as installation instructions are provided [here](https://github.com/kausiksivakumar/safe_reinforcement_learning).
