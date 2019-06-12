---
title: "Arc-support Line Segments Revisited: An Efficient High-quality Ellipse Detection"
collection: publications
permalink: /publication/2018-09-24-High-quality-Ellipse-Detection/
excerpt: '> *> **Changsheng Lu**, Siyu Xia, Ming Shao and Yun Fu*<br>> Over the years many ellipse detection algorithms spring up and are studied broadly, while the critical issue both accurately and efficiently detecting ellipses in real-world images still remains a challenge such that we cannnot find an applicable ellipse detector from Matlab and OpenCV. The main research task of paper is to propose an accurate and efficient ellipse detecotr.'
date: 2018-09-24
venue: '--'
#paperurl: 'https://ieeexplore.ieee.org/document/8296246/'
#citation: 'Changsheng Lu, Siyu Xia, Wanming Huang, Ming Shao, Yun Fu. Circle Detection by Arc-support Line Segments. In: The 24rd IEEE International Conference on Image Processing (ICIP).'
---

<!-- Journal: -->
<!-- === -->
<!-- Submitted to IEEE Transactions on Image Processing -->  

Authors: 
===
**Changsheng Lu**, [Siyu Xia](https://automation.seu.edu.cn/2019/0528/c24505a275207/page.htm), [Ming Shao](http://www.cis.umassd.edu/~mshao/) and [Yun Fu](http://www1.ece.neu.edu/~yunfu/)

Abstract: 
===
Over the years many ellipse detection algorithms spring up and are studied broadly, while the critical issue both accurately and efficiently detecting ellipses in real-world images still remains a challenge. In this paper, an accurate and efficient ellipse detector by arc-support line segments is proposed. The arc-support line segment simplifies the complicated expression of curves in the image while keeping the general properties like convexity and polarity, which grounds the successful detection of ellipses. The arc-support groups are formed by iteratively and robustly linking the arc-support line segments that latently belonging to a common ellipse at point statistics level. Afterward, two complementary approaches, namely selecting the group with higher saliency to fit the ellipse directly and searching all the valid paired arc-support groups through three novel constraints, are utilized to generate the initial ellipse set both locally and globally. During the ellipse fitting step, a superposition principle of the fast ellipse fitting is developed to accelerate the fitting process. Then the ellipse candidates can be formulated by hierarchically clustering the decomposed 5D parameter space of initial ellipse set. Finally, the salient ellipse candidates are picked out as detections under the stringent and effective verification. Extensive experiments on three public datasets are implemented and our method achieves the best F-measure scores compared to the state-of-the-art ellipse detection algorithms, which highlights the high-quality detection performance of the proposed method.  

More details:
===  
- Matlab Version Source Code: Please click [here](https://github.com/AlanLuSun/High-quality-ellipse-detection).  
<!-- - [Download paper](https://arxiv.org/abs/1810.03243v3).-->
