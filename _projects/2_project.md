---
layout: page
title: Explaining Recurrent Attention Models (RAM)
description: This project explains the working of RAM models by adding a variational autoencoder and analyzing image reconstructions with respect to image glimpses.
img: assets/img/ESE546_RAM/ram_cluttered.png
importance: 2
category: work
github: https://github.com/kausiksivakumar/Recurrent_Attention_Model
---

The Recurrent Attention Model (RAM) is a neural network that processes inputs sequentially, attending to different locations (glimpses) within the image one at a time, and incrementally combining information from these fixations to build up a dynamic internal representation of the image. Unlike in the deep convolution network, in hard attention it is explainable which regions of the image contributed to the prediction. To infer the glimpses and explain the model qualitatively, we build a Variational Autoencoder (VAE) on the final hidden state of the recurrent units and visualize the reconstruction of the images after each glimpse is processed. We also prove quantitatively the model encodes some latent space statistics of the entire image through a sequence of patches by evaluating the expected information gain(EIG) over the classification output after each glimpse. These are demonstrated on the MNIST and cluttered MNIST dataset. We also attempted to study the improvement in the above statistics through reward shaping the inherent reinforcement learning algorithm that dictates where to see next. We report that the new reward structure performs better than the original one used in the [paper](https://proceedings.neurips.cc/paper/2014/file/09c6c3783b4a70054da74f2538ed47c6-Paper.pdf) in terms of information gain over the MNIST dataset.

The qualitative visualizations of the reconstructions are provided below
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE546_RAM/ram_org.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    MNIST image reconstruction(leftmost original MNIST image, followed by reconstruction output with each glimpse taken)
</div>

We also add noise to the input image to stress-test the robustness of RAM models
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE546_RAM/ram_cluttered.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    MNIST Cluttered image reconstruction(leftmost original MNIST image, second original MNIST cluttered image, followed by reconstruction output with each glimpse taken)
</div>

The existing approach  provides a reward value of 1 if, at the end of n glimpses if the network classifies the image correctly (Hard Attention). We also wanted the network to be very confident in its classification logits. Thus, we added a self entropy term, that tries to make this classification richer at every glimpse (Hard Attention Reshaped)
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE546_RAM/Information_gain_MNIST.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ESE546_RAM/Information_gain_MNIST_clut.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Information gain on MNIST and MNIST cluttered dataset. HardAtt(existing method) HardAttReshaped(our contribution)
</div>
We can see that for MNIST, our reshaped reward helps get more information gain than the hard attention model proposed. This is expected as with the new reward the network also optimises over the certainty of its classification. But, for the cluttered dataset the model with reward shaping underperforms in terms of  information gain. We believe this to be due to the presence of distractions which are falsely rewarded, and hence the model is unable to make the distribution of its softmax probabilities more Dirac.

Our code implementation is provided [here](https://github.com/kausiksivakumar/Recurrent_Attention_Model).