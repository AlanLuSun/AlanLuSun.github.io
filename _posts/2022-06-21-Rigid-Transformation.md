---
title: Rigid Transformation in Euclidean Space
date: 2022-03-10
permalink: /posts/2022-06-21-Rigid-Transformation/
excerpt: ""
tags:
  - Learning Notes
---

*Author: Changsheng Lu (卢长胜)*

## Outline
- Notations
- Rigid Transformation
- Pose Estimation
- Camera Relocalization

## Notations
Here comes notations, ...




## Motivation
The softmax is nice normalizer whose formulation is $p=\exp(f^{\theta}(x))/\sum_{i}^{C}\exp(f^{\theta}_{i}(x))$. However, when $C$ is tremendous, it requires much time to compute the summation of all classes' activations. To save time, the researchers propose to use *Noise Contrastive Estimation (NCE)* which samples negative noise for contrastive learning, thus we only need to compute the $c$-th activations for both postive sample and negative samples.

The key idea behind NCE [1,2,3] and also the following infoNCE [4] aim to maximize the activation value (or signal value) from postive samples while surpressing those values (or noise values) from negative samples, which forms contrastive learning. This has a solid mathematical proof in [Noise Contrastive Estimation](https://leimao.github.io/article/Noise-Contrastive-Estimation/).


## Mathematical Formulation for NCE Loss
$$
J(\theta)=E_{w\sim P_{d}(w)}[\log \sigma(\triangle f^{\theta}(w))] + kE_{w \sim P_{noise}(w)}[\log (1- \sigma(\triangle f^{\theta}(w)))]
$$  
where $\sigma=\frac{1}{1+e^{-1}}$ is the sigmoid function, $\triangle f^{\theta}(w) = f^{\theta}(w) - \log kP_{noise}(w)$. Its empirical form is  
$$
\hat{J}(\theta)=\frac{1}{m}\sum_{i=1}^{m} \log \sigma(\triangle f^{\theta}(w_i)) +\frac{k}{n}\sum_{j=1}^{n} \log (1- \sigma(\triangle f^{\theta}(w_j)))
$$  
where $m$ is the number of positive samples and $n$ is number of noise samples. $k$ is the draw number for noise.  

Remarks: The former part of formulation is to maximize signal while the latter part is to supress noise, forming the contrastive learning.


## The infoNCE and Contrastive Predictive Coding (CPC)
The infoNCE's formulation is  
$$
L_{infoNCE}=-E_{X} \log \frac{f_{k}(x_{t+k}, c_t)}{\sum_{x_{j} \in X} f_{k}(x_{j}, c_{t})}
$$  
where $(x_{t+k}, c_t)$ is a postive pair, $(x_{j}, c_{t}), j=1,2,\cdots, |X|$ are negative pairs. $f_{k}(x_{t+k}, c_t)=\exp(.)$ is the model output. 

CPC is used in language models which improves the feature representation ability by measuring a repres feature's prediction ability over following words. *A good repres feature should preserve the important information contained in raw data while also have good prediction ability (for subsequent words)*, e.g., knowing several first words in a sentence will result in a guess for subsequent words. In [4], CPC is formed by   
$$
f_{k}(x_{t+k}, c_{t}) = \exp (z^{T}_{t+k}W_{k}c_{t})
$$  
where $z_{t+k}=g_{encoder}(x_{t+k})$, and $W_{k}c_{t}$ is a guess for $z_{t+k}$ by using $t$-th time step's information $c_{t}$.


## Resources
- [Noise Contrastive Estimation](https://leimao.github.io/article/Noise-Contrastive-Estimation/)
- [InfoNCE and CPC, 知乎](https://zhuanlan.zhihu.com/p/129076690)
- [CSDN](https://blog.csdn.net/m0_37876745/article/details/110933812?utm_medium=distribute.pc_aggpage_search_result.none-task-blog-2~aggregatepage~first_rank_ecpm_v1~rank_v31_ecpm-2-110933812.pc_agg_new_rank&utm_term=infonce%E6%8D%9F%E5%A4%B1&spm=1000.2123.3001.4430)


## References
[1] Gutmann, Michael, and Aapo Hyvärinen. "Noise-contrastive estimation: A new estimation principle for unnormalized statistical models." Proceedings of the thirteenth international conference on artificial intelligence and statistics. JMLR Workshop and Conference Proceedings, 2010.  
[2] Mnih, Andriy, and Yee Whye Teh. "A fast and simple algorithm for training neural probabilistic language models." arXiv preprint arXiv:1206.6426 (2012).  
[3] Mnih, Andriy, and Koray Kavukcuoglu. "Learning word embeddings efficiently with noise-contrastive estimation." Advances in neural information processing systems 26 (2013).  
[4] Van den Oord, Aaron, Yazhe Li, and Oriol Vinyals. "Representation learning with contrastive predictive coding (CPC)." arXiv e-prints (2018): arXiv-1807.  

