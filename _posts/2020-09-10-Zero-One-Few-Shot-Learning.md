---
title: Zero/One/Few Shot Learning
date: 2020-09-10
permalink: /posts/2020-09-10-Zero-One-Few-Shot-Learning/
excerpt: quick cookbook on Zero/One/Few Shot Learning
tags:
  - Learning Notes
---

# Zero/One/Few Shot Learning  
*Author: Changsheng Lu (卢长胜)*

## 1、Zero-Shot Learning  
### Problem definition:  
   Learning a model to work on unseen data when training and testing classes are disjoint. Taking the task of one-shot object classification as an example, when training an object classifier, there is no training samples of target classes. While in testing phase, we expect the object classifier could recognize the unseen target object to be a new class.

### Methods:
   - Attribute-based method [1]
   - 

### Dataset:
   - [Animals with Attributes (AWA)](https://cvml.ist.ac.at/AwA2/)
   - 

### References
[1] Lampert, Christoph H., Hannes Nickisch, and Stefan Harmeling. "Learning to detect unseen object classes by between-class attribute transfer." In 2009 IEEE Conference on Computer Vision and Pattern Recognition, pp. 951-958. IEEE, 2009.  
[2] 


## 2、One-Shot Learning 



## 3、Few-Shot Learning  
### Methods:
   - Model-based method  
     Memory augmented model [3]
   - Metric-based method  
     Siamese Network [1] , Prototype Network [2]
   - Optimization-based method  
     Learn a model to reach a good parameter status (compared to directly use related model or randomly initialized model) for finetuning in expectance of obtaining better performance.

### References
[1] Koch, Gregory, Richard Zemel, and Ruslan Salakhutdinov. "Siamese neural networks for one-shot image recognition." ICML Deep Learning Workshop. Vol. 2. 2015.  
[2] Snell, Jake, Kevin Swersky, and Richard Zemel. "Prototypical networks for few-shot learning." Advances in Neural Information Processing Systems. 2017.  
[3] Santoro A, Bartunov S, Botvinick M, et al. One-shot learning with memory-augmented neural networks[J]. arXiv preprint arXiv:1605.06065, 2016.  
[4] 