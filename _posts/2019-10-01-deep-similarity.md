---
title: "Deep Siamese CNN for Learning Visual Similarity"
date: 2019-10-01
tags: [machine learning, deep learning ,computer vision]
excerpt: "Learning a pose-invariant feature space for visual search"
mathjax: "true"
---

<img src="{{ site.url }}{{ site.baseurl }}/images/architecture.jpg" alt="Siamese CNN">

Developed a multi-task Siamese CNN for transforming images of apparels to a latent space where images of visually similar items and same item in different poses were close together. 
**Dataset:** Images of apparels from e-commerce fashion website [Abof](https://www.abof.com/) with 25 different labels, alongwith different poses each apparel item
* Used GoogleNet (pre-trained on [ImageNet](http://www.image-net.org/) dataset) and used **transfer-learning** for fine-tuning model for classification task on apparel dataset.
* **Multi-task learning** : Used the above network in a Siamese architecture, and trained it on pairs of images using Contrastive-Divergence (CD) loss function
$$L(\theta)$$
* A positive pair is defined if the second image is the same item in a different pose, this allows us to learn a pose-invariant embedding space
* Created a visual search algorithm that used nearest neighbor matching on the pose-invariant embedding space for finding stylistically similar products

