---
title: "Deep Siamese CNN for Learning Visual Similarity"
date: 2019-10-01
tags: [projects]
excerpt: "Learning a pose-invariant feature space for visual search"
mathjax: "true"
---

<img src="{{ site.url }}{{ site.baseurl }}/images/siamese.jpg" alt="Siamese CNN">

Developed a multi-task Siamese CNN for transforming images of apparels to a latent space where images of visually similar items and same item in different poses were close together. 

**Dataset:** Images of apparels from e-commerce fashion website [Abof](https://www.abof.com/) with 25 different labels, alongwith different poses of each apparel item
* Used GoogleNet (pre-trained on [ImageNet](http://www.image-net.org/) dataset) and used **transfer-learning** for fine-tuning model for classification task on apparel dataset.
* **Multi-task learning** : Used the above network in a Siamese architecture, and trained it on pairs of images using Contrastive-Divergence (CD) loss function

$$L(\theta) = \sum_{(x_{q}, x_{p})} L_{p}(x_{q},x_{p}) + \sum_{(x_{q}, x_{n})} L_{n}(x_{q},x_{n})$$

Here, $$L_{p}$$ is the penalty for similar images that are far away and $$L_{n}$$ is the penalty for dissimilar images that are nearby,

$$L_{p}(x_{q},x_{p}) = ||x_{q} - x_{p}||_{2}^{2}$$

$$L_{n}(x_{q},x_{n}) = max(0, m^{2} - ||x_{q} - x_{n}||_{2}^{2})$$



* A positive pair is defined if the second image is the same item in a different pose, this allows us to learn a pose-invariant embedding space
* Created a visual search algorithm that used nearest neighbor matching on the pose-invariant embedding space for finding stylistically similar products

