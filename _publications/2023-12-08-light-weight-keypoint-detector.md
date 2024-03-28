---
title: "Detect Any Keypoints: An Efficient Light-Weight Few-Shot Keypoint Detector"
collection: publications
permalink: /publication/2023-12-08-light-weight-keypoint-detector/
excerpt: '> *>The 38th Annual AAAI Conference on Artificial Intelligence (AAAI 2024)*<br>*>**Changsheng Lu**, Piotr Koniusz*<br>>In order to maintain flexibility of detecting varying number of keypoints, existing few-shot keypoint detection (FSKD) approaches modulate query feature map per support keypoint, then detect the corresponding keypoint from each modulated feature via a detection head. Such modulation-detection separate design would scale up model into heavy yet slow one when the number of keypoints increases. To overcome this issue, we design a novel light-weight detector which combines modulation and detection into one step, greatly reducing the computational cost without sacrifice of performance. Moreover, to bridge the large domain shift of keypoints between seen and unseen species, we further improve our model with mean feature based contrastive learning to align keypoint distributions that encourage better keypoint representations for FSKD.'
date: 2023-12-08
venue: '--'
#paperurl: 'https://ieeexplore.ieee.org/document/8296246/'
#citation: 'Changsheng Lu, Siyu Xia, Wanming Huang, Ming Shao, Yun Fu. Circle Detection by Arc-support Line Segments. In: The 24rd IEEE International Conference on Image Processing (ICIP).'
#Pay attention!!! date 2022-06-10 should be former than today (2022-06-12) as it will triger error.
---

Conference:  
===  
The 38th Annual AAAI Conference on Artificial Intelligence (AAAI 2024)

Authors: 
===
**Changsheng Lu**, [Piotr Koniusz](http://users.cecs.anu.edu.au/~koniusz/)

Quickview:
===  
<img src="/images/pub-images/2024/lwfskd.png" width="100%" height="100%">

Abstract: 
===
Recently the ``prompt'' based models are popular across various language and vision tasks. With similar spirit, we are curious about detecting any keypoints on a query image, given the prompts of support image and keypoints. This problem is also called as few-shot keypoint detection (FSKD), which has crucial applications of detecting keypoints or poses on diverse animals. In order to maintain flexibility of detecting varying number of keypoints, existing FSKD approaches modulate query feature map per support keypoint, then detect the corresponding keypoint from each modulated feature via a detection head. Such modulation-detection separate design would scale up model into heavy yet slow one when the number of keypoints increases. To overcome this issue, we design a novel light-weight detector which combines modulation and detection into one step, greatly reducing the computational cost without sacrifice of performance. Moreover, to bridge the large domain shift of keypoints between seen and unseen species, we further improve our model with mean feature based contrastive learning to align keypoint distributions that encourage better keypoint representations for FSKD. Compared to the state of the arts, our light-weight detector saves more than 50\% parameters, training and test time, while achieves 5.62\% improvements on 1-shot novel keypoint detection on animal pose dataset. Our model is also robust to the number of evaluated keypoints, saves much memory when evaluating large amounts of (\eg, 1000) keypoints.  

<!-- Source Code: 
===
Please click [here](https://github.com/AlanLuSun/Few-shot-keypoint-detection). -->