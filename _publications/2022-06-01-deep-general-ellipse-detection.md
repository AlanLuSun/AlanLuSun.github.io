---
title: "ElDet: An Anchor-free General Ellipse Object Detector"
collection: publications
permalink: /publication/2022-06-01-deep-general-ellipse-detection/
excerpt: '> *>Asian Conference on Computer Vision (ACCV 2022, to appear)*<br>*>Tianhao Wang, **Changsheng Lu**, Ming Shao, Xiaohui Yuan, Siyu Xia*<br>>Ellipse detection is a fundamental task in object shape analysis. Under complex environments, the traditional image processing based approaches may under-perform due to the hand-crated features. Instead, CNN-based approaches are more robust and powerful. In this paper, we introduce an efficient anchor-free data-augmentation based general ellipse detector, termed ElDet.'
date: 2022-06-01
venue: '--'
#paperurl: 'https://ieeexplore.ieee.org/document/8296246/'
#citation: 'Changsheng Lu, Siyu Xia, Wanming Huang, Ming Shao, Yun Fu. Circle Detection by Arc-support Line Segments. In: The 24rd IEEE International Conference on Image Processing (ICIP).'
---

Conference:  
===  
Asian Conference on Computer Vision (ACCV 2022)

Authors: 
===
Tianhao Wang, **Changsheng Lu**, Ming Shao, Xiaohui Yuan, Siyu Xia

Abstract: 
===
Ellipse detection is a fundamental task in object shape analysis. Under complex environments, the traditional image processing based approaches may under-perform due to the hand-crated features. Instead, CNN-based approaches are more robust and powerful. In this paper, we introduce an efficient anchor-free data-augmentation based general ellipse detector, termed ElDet. Different from existing CNN-based methods, our ElDet relies more on edge information which could excavate more shape information into learning. Specifically, we first develop an edge fusion module to composite an overall edge map which has more complete boundary and better continuity. The edge map is treated as augmentation input for our ElDet for ellipse regression. Secondly, three loss functions are tailored to our ElDet, which are angle loss, IoU loss, and binary mask prediction loss to jointly improve the ellipse detection performance. Moreover, we contribute a diverse ellipse dataset by collecting multiple classes of elliptical objects in real scenes. Extensive experiments show that the proposed ellipse detector is very competitive to state-of-the-art methods.  
