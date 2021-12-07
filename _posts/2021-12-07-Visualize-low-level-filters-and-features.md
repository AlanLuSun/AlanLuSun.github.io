---
title: Techniques to Visualize Low-level Filters and Features
date: 2021-12-07
permalink: /posts/2021-12-07-Visualize-low-level-filters-and-features/
excerpt: ""
tags:
  - Learning Notes
---

# Techniques to Visualize Low-level Filters and Features
*Author: Changsheng Lu (卢长胜)*

## Visualization for Learned Filters in CNN
In order to understand the internal representations learned by CNN, in many cases, we would like to visualize what CNN has learned in each layer, and especially see the trends from low-level to high-level. Since it's trivial to directly map a feature map (by selecting a channel or merging all channels) to greyscale image (or RGB image), one is reasonable to see the max response w.r.t. a specific filter. The techniques include:
- Learnable image editting. By taking a learnable noise image $I$ as input, we obtain the feature output $F^{l}$ from a specific fiter $K^l$. Let the loss be $L=\sum F^{l}$. Then, we could acquire the gradients w.r.t. $I$ as $\partial L^l/\partial I$, and update $I:=I+\eta\cdot\frac{\partial L^l}{\partial I}$. After several iterations, we are hopefully to acquire the image $I$ which enable the specific fiter $K^l$ to have maximal response.


## Visualization for Learned Feature Maps in CNN
- CAM [1]
- Grad-CAM (preferred) [2]



## Some Materials
- [知乎](https://zhuanlan.zhihu.com/p/53683453)


## References
[1] Zhou, Bolei, et al. "Learning deep features for discriminative localization." Proceedings of the IEEE conference on computer vision and pattern recognition. 2016.  
[2] Selvaraju, Ramprasaath R., et al. "Grad-cam: Visual explanations from deep networks via gradient-based localization." Proceedings of the IEEE international conference on computer vision. 2017.  
[3] 

