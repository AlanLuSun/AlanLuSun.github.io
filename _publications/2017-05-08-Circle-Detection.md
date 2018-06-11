---
title: "Circle Detection by Arc-support Line Segments"
collection: publications
permalink: /publication/2017-09-20-Circle-Detection/
excerpt: '> *> 2017 IEEE International Conference on Image Processing (ICIP)*<br>> ***Changsheng Lu**, Siyu Xia, Wanming Huang, Ming Shao and Yun Fu*<br>> We propose a novel method for circle detection by analysing and refining arc-support line segments. The key idea is to use line segment detector to extract the arc-support line segments which are likely to make up the circle, instead of all line segments. Each couple of line segments is analyzed to form a valid pair and followed by generating initial circle set. Through the mean shift clustering, the circle candidates are generated and verified based on the geometric attributes of circle edge. Finally, twice circle fitting is applied to increase the accuracy for circle locating and radius measuring.'
date: 2017-05-08
venue: 'IEEE International Conference on Image Processing (ICIP)'
#paperurl: 'https://ieeexplore.ieee.org/document/8296246/'
#citation: 'Changsheng Lu, Siyu Xia, Wanming Huang, Ming Shao, Yun Fu. Circle Detection by Arc-support Line Segments. In: The 24rd IEEE International Conference on Image Processing (ICIP).'
---

Coference:
===
2017 IEEE International Conference on Image Processing (ICIP)

Authors: 
===
**Changsheng Lu**, [Siyu Xia](http://automation.seu.edu.cn/Articles.aspx?id=2310), Wanming Huang, [Ming Shao](http://www.cis.umassd.edu/~mshao/) and [Yun Fu](http://www1.ece.neu.edu/~yunfu/)

Abstract: 
===
Circle detection is fundamental in both object detection and high accuracy localization in visual control systems. We propose a novel method for circle detection by analysing and refining arc-support line segments. The key idea is to use line segment detector to extract the arc-support line segments which are likely to make up the circle, instead of all line segments. Each couple of line segments is analyzed to form a valid pair and followed by generating initial circle set. Through the mean shift clustering, the circle candidates are generated and verified based on the geometric attributes of circle edge. Finally, twice circle fitting is applied to increase the accuracy for circle locating and radius measuring. The experimental results demonstrate that the proposed method performs better than other well known approaches on circles that are incomplete, occluded, blurry and over-illumination. Moreover, our method shows significant improvement in accuracy, robustness and efficiency on the industrial Printed Circuit Board (PCB) images as well as the synthesized, natural and complicated images.  

More details:
===  
- Matlab Version Source Code: Please click [here](https://github.com/AlanLuSun/Circle-detection).  
- C++ Version Source Code: Will be released soon.  
- [Download paper](https://AlanLuSun.github.io/files/ICIP 2017-Circle detection.pdf).