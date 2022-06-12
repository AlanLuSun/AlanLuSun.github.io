---
title: "Few-Shot Keypoint Detection With Uncertainty Learning for Unseen Species"
collection: publications
permalink: /publication/2022-06-12-few-shot-keypoint-detection/
excerpt: '> *>IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR 2022)*<br>*>**Changsheng Lu**, Piotr Koniusz*<br>>Current non-rigid object keypoint detectors perform well on a chosen kind of species and body parts, and require a large amount of labelled keypoints for training. Moreover, their heatmaps, tailored to specific body parts, cannot recognize novel keypoints (keypoints not labelled for training) on unseen species. In this paper, we propose a versatile Few-shot Keypoint Detection (FSKD) pipeline which could not only detect base keypoints but also novel keypoints for unseen species.'
date: 2022-06-12
venue: '--'
#paperurl: 'https://ieeexplore.ieee.org/document/8296246/'
#citation: 'Changsheng Lu, Siyu Xia, Wanming Huang, Ming Shao, Yun Fu. Circle Detection by Arc-support Line Segments. In: The 24rd IEEE International Conference on Image Processing (ICIP).'
---

Conference:  
===  
[IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR'22)](https://openaccess.thecvf.com/content/CVPR2022/html/Lu_Few-Shot_Keypoint_Detection_With_Uncertainty_Learning_for_Unseen_Species_CVPR_2022_paper.html) (Top conference in the field of computer vision)  

Authors: 
===
**Changsheng Lu**, [Piotr Koniusz](http://users.cecs.anu.edu.au/~koniusz/)

Quickview:
===  
[<img src="/images/pub-images/2022/fskd.png" width="60%" height="60%">](https://openaccess.thecvf.com/content/CVPR2022/html/Lu_Few-Shot_Keypoint_Detection_With_Uncertainty_Learning_for_Unseen_Species_CVPR_2022_paper.html)  

Abstract: 
===
Current non-rigid object keypoint detectors perform well on a chosen kind of species and body parts, and require a large amount of labelled keypoints for training. Moreover, their heatmaps, tailored to specific body parts, cannot recognize novel keypoints (keypoints not labelled for training) on unseen species. We raise an interesting yet challenging question: how to detect both base (annotated for training) and novel keypoints for unseen species given a few annotated samples? Thus, we propose a versatile Few-shot Keypoint Detection (FSKD) pipeline, which can detect a varying number of keypoints of different kinds. Our FSKD provides the uncertainty estimation of predicted keypoints. Specifically, FSKD involves main and auxiliary keypoint representation learning, similarity learning, and keypoint localization with uncertainty modeling to tackle the localization noise. Moreover, we model the uncertainty across groups of keypoints by multivariate Gaussian distribution to exploit implicit correlations between neighboring keypoints. We show the effectiveness of our FSKD on (i) novel keypoint detection for unseen species, and (ii) few-shot Fine-Grained Visual Recognition (FGVR) and (iii) Semantic Alignment (SA) downstream tasks. For FGVR, detected keypoints improve the classification accuracy. For SA, we showcase a novel thin-plate-spline warping that uses estimated keypoint uncertainty under imperfect keypoint corespondences.  

More details:
===  
- Paper can be found [here](https://openaccess.thecvf.com/content/CVPR2022/html/Lu_Few-Shot_Keypoint_Detection_With_Uncertainty_Learning_for_Unseen_Species_CVPR_2022_paper.html).  
<!-- - [Download paper](https://arxiv.org/abs/1810.03243v3).-->
