---
title: Rigid Transformation in Euclidean Space
date: 2022-06-20
permalink: /posts/2022-06-21-Rigid-Transformation/
excerpt: ""
tags:
  - Learning Notes
---

*Author: Changsheng Lu (卢长胜)*

## Outline
- [X] Notations
- [X] Rigid Transformation
- [X] Pose Estimation
- [X] Camera Relocalization

## Notations
|             |  Definition |
|:------------|:-----------:|
| $SE(3)$     | Rigid transformations in 3D Euclidean space|
| $R$         | Rotation matrix |
| $t$         | Translation (homogeneous coordinate $[x, y, 1]^{T}$)
| $P \in SE(3)$ | Pose (Orientation+Position) or rigid transformation |


## Rigid Transformation
### Kinematics
The pose $P$ of an object or a rigid transformation $T$ can be represented by a $4 \times 4$ matrix 
$$
T=\left[
  \begin{matrix}
    R & t \\
    0 & 1
  \end{matrix}
  \right]_{4 \times 4}
$$
Namely, $T=[R|t]$, or $T \in SE(3)$, $P \in SE(3)$.


**Coordinate system:**
- world coordinate system
- camera coordinate system
- optical coordinate system (In many cases, it assumes to be same with camera coordinate system but in practice they are different.)
- object coordinate system

**Left multiplication rule:** $T=T^{n}\cdots T^{2}T^{1}$, if $T^i$ is the rigid transformation relative to same base coordinate system $O$. The transformation sequence is $T^{1},T^{2},\cdots,T^{n}$.

**Right multiplication rule:** $T=T^{1}\cdots T^{n-1}T^{n}$, if $T^i$ is the rigid transformation relative to previous pose (or previous coordinate system $O_{i-1}$). The transformation sequence is $T^{1},T^{2},\cdots,T^{n}$.

**Inverse of rigid transformation:** Assume $T=[R|t]$, then its inverse is $T^{-1}=[R^{-1}|-R^{-1}t]$. This could be easily proved by computing below linear system 
$$
XT=I \\
X=T^{-1}=\left[
  \begin{matrix}
    R^{-1} & -R^{-1}t \\
    0      & 1
  \end{matrix}
  \right]
$$
It should note that, the inverse of rigid transformation $X$ can also be decomposed to *a translation transformation* followed by *a rotation transformation* as follows:
$$
X=\left[
  \begin{matrix}
    R^{-1} & 0 \\
    0      & 1
  \end{matrix}
  \right]
  \left[
  \begin{matrix}
    I & -t \\
    0 & 1
  \end{matrix}
  \right]
$$
This meets our direct imagination as we could firstly move object to a point in opposite direction and then rotate the object.



## Pose Estimation
**Ingredients:** 1) two images of same scene ($I^a, I^b$) (captured at two different camera poses); 2) depth maps ($D^a, D^b$); 3) camera intrinsic parameters ($K$); 4) two sets of corresponding keypoints ($p^a_1,\cdots,p^a_n$) and ($p^b_1,\cdots,p^b_n$); 5) relative pose $T\in SE(3)$ between two camera poses.

**Tasks:** 1) The relative pose could be estimated when knowing remaining conditions; 2) The depth could be estimated when knowing remaining conditions.




## Camera Relocalization
**Camera relocalization** task usually assumes the scene is given, the initial camera pose is given, and only the camera pose will change over time. Thus, we could estimate camera pose to realize camera relocalization, for example, calibrating camera pose to reference pose. Thus, we could estimate camera pose based on a pair of (reference image, current image) under such setting.

Inherently, camera relocalization is also a sub-problem of pose estimation. The *active viewpoint transfer* problem is exactly the *camera relocalization*.











## Resources
- [Noise Contrastive Estimation](https://leimao.github.io/article/Noise-Contrastive-Estimation/)
- [InfoNCE and CPC, 知乎](https://zhuanlan.zhihu.com/p/129076690)
- [CSDN](https://blog.csdn.net/m0_37876745/article/details/110933812?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-2-110933812.pc_agg_new_rank&utm_term=infonce%E6%8D%9F%E5%A4%B1&spm=1000.2123.3001.4430)


## References
[1] Gutmann, Michael, and Aapo Hyvärinen. "Noise-contrastive estimation: A new estimation principle for unnormalized statistical models." Proceedings of the thirteenth international conference on artificial intelligence and statistics. JMLR Workshop and Conference Proceedings, 2010.  
[2] Mnih, Andriy, and Yee Whye Teh. "A fast and simple algorithm for training neural probabilistic language models." arXiv preprint arXiv:1206.6426 (2012).  
[3] Mnih, Andriy, and Koray Kavukcuoglu. "Learning word embeddings efficiently with noise-contrastive estimation." Advances in neural information processing systems 26 (2013).  
[4] Van den Oord, Aaron, Yazhe Li, and Oriol Vinyals. "Representation learning with contrastive predictive coding (CPC)." arXiv e-prints (2018): arXiv-1807.  

