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

## 1、Zero-shot Learning  
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


## 2、Few-shot Learning  
### Definition:  
  Few-shot learning refers to understand new concepts from only a *few* examples.

### Methods:
   - Model-based method  
     Memory augmented model [1]
   - Metric-based method  
     Siamese Network [2] , Prototype Network [3], Match Network [4] 
   - Optimization-based method  
     Learn a model to reach a good parameter status (compared to directly use related model or randomly initialized model) for finetuning in expectance of obtaining better performance.  
     Methods: Model-agnostic meta-learning [5]

### Loss functions
  - Cross entropy loss  
    $L = Ylog(P) + (1-Y)log(1-P)$
  - Contrasive loss  
    $L = (1-Y)\frac{1}{2}D^{2} + Y\frac{1}{2}\{max(0, m-D)\}^2$  
    where $D$ is the distance function acted for embeddings. So the loss will decrease the distance D when the samples are from the same class, on the other hand when they are dissimilar it will try to increase D with a certain margin m. The margin purpose is to neglect samples that have larger distance than m, since we only want to focus on dissimilar samples that appear to be close.
  - Triplet loss  
    $L = max(D(X, X^{+}) - D(X, X^{-}) + m, 0)$


### Dataset:
   - [Omniglot](https://github.com/brendenlake/omniglot) [6], the few-shot version of MNIST.
   - Mini-ImageNet [4]


### References
[1] Santoro A, Bartunov S, Botvinick M, et al. One-shot learning with memory-augmented neural networks[J]. arXiv preprint arXiv:1605.06065, 2016. 
[2] Koch, Gregory, Richard Zemel, and Ruslan Salakhutdinov. "Siamese neural networks for one-shot image recognition." ICML Deep Learning Workshop. Vol. 2. 2015.  
[3] Snell, Jake, Kevin Swersky, and Richard Zemel. "Prototypical networks for few-shot learning." Advances in Neural Information Processing Systems. 2017.   
[4] Oriol Vinyals, Charles Blundell, Tim Lillicrap, Daan Wierstra, et al. Matching networks for one shot learning. In Advances in Neural Information Processing Systems, pages 3630–3638, 2016.  
[5] Finn, Chelsea, Pieter Abbeel, and Sergey Levine. "Model-agnostic meta-learning for fast adaptation of deep networks." Proceedings of the 34th International Conference on Machine Learning-Volume 70. JMLR. org, 2017.  
[6] Lake, Brenden, et al. “One shot learning of simple visual concepts.” Proceedings of the Annual Meeting of the Cognitive Science Society. Vol. 33. No. 33. 2011.  
[7] Hoffer, Elad, and Nir Ailon. “Deep metric learning using triplet network.” International Workshop on Similarity-Based Pattern Recognition. Springer, Cham, 2015.



## 3、One-shot Learning 
One-shot learning is a particular case of few-shot learning when 'shot' $k = 1$.