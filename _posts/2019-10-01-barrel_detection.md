---
title: "Probabilistic Color Model for Segmentation"
date: 2019-10-01
tags: [projects]
excerpt: "Logistic regression and shape heuristics for segmentation"
mathjax: "true"
---

[Github](https://github.com/ijssaggu/Barrel-Detection), [Report](/files/barrel_detection.pdf)

<img src="{{ site.url }}{{ site.baseurl }}/images/normal.jpg" alt="normal-light">

Trained a probabilistic color model based on logistic regression on image data and used it to segment unseen images, detect a blue barrel, and draw a bounding box around it. 
Once the color regions were identified, shape statistics and other higher-level features were used to define "barrelness" and decide where the barrel is located in the images.