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
   Learning a model to work on unseen data when training and testing classes are disjoint. Taking the task of zero-shot object classification as an example, when training an object classifier, there is no training samples of target classes. While in testing phase, we expect the object classifier could recognize the unseen target object to be a new class.

### Methods:
   - Attribute-based method [1]
   - Attribute Label Embedding (ALE) [2]
   - Zero-shot Kernel Learning (ZSKL) [3]

### Dataset:
   - [Animals with Attributes (AWA)](https://cvml.ist.ac.at/AwA2/)
   - 

### References
[1] Lampert, Christoph H., Hannes Nickisch, and Stefan Harmeling. "Learning to detect unseen object classes by between-class attribute transfer." In 2009 IEEE Conference on Computer Vision and Pattern Recognition, pp. 951-958. IEEE, 2009.  
[2] Akata, Zeynep, Florent Perronnin, Zaid Harchaoui, and Cordelia Schmid. "Label-embedding for attribute-based classification." In Proceedings of the IEEE conference on computer vision and pattern recognition, pp. 819-826. 2013.  
[3] Zhang, Hongguang, and Piotr Koniusz. "Zero-shot kernel learning." In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pp. 7670-7679. 2018.  

## 2、Few-shot Learning  
### Definition:  
  Few-shot learning refers to understand new concepts from only a *few* examples.

### A Taxonomy of Methods:
   - Metric-based method (Prior knowledge about similarity)  
     - Siamese Network (Koch et al., 2015) [2] (pairwise comparator + predefined distance metric)
     - Triplet Network (Hoffer & Ailon, 2015) [7] (pairwise comparator + predefined metric)
     - Matching Network (Oriol et al., 2016) [3] (multi-class comparator + predefined metric)
     - Prototype Network (Snell et al., 2017) [4] (multi-class comparator + predefined metric)  
     - Relation Networks (Santoro et al., 2016) [1] (use relation/similarity network in replace of pre-defined distance metric like [2-4, 7])
   - Optimization-based method (Prior knowledge about learning)  
     Learn a model with a good parameter status (compared to directly use related model or randomly initialized model) to be easier to finetune or adapt.  
     Methods: 
     - Bayesian approach [8]  
     - Model-agnostic meta-learning (MAML) (Finn & Levine, 2017) [5]
   - Data-based method (Prior knowledge about data)  
    1) Lean a generative model for family of classes or 2) Learn to synthesize new examples and train with augmented data
      

### Loss functions
  - Cross entropy loss  
    $L = Ylog(P) + (1-Y)log(1-P)$
  - Contrasive loss  
    $L = (1-Y)\frac{1}{2}D^{2} + Y\frac{1}{2}\{max(0, m-D)\}^2$  
    where $D$ is the distance function acted for embeddings. So the loss will decrease the distance D when the samples are from the same class, on the other hand when they are dissimilar it will try to increase D with a certain margin m. The margin purpose is to neglect samples that have larger distance than m, since we only want to focus on dissimilar samples that appear to be close.
  - Triplet loss [7]  
    $L = max(D(X, X^{+}) - D(X, X^{-}) + m, 0)$


### Dataset:
   - [Omniglot](https://github.com/brendenlake/omniglot) [6], the few-shot version of MNIST. This dataset has 1623 characters from 50 alphabets. In each class, there are 20 samples drawn by 20 peoples. Each image has size of 105 x 105.
   - Mini-ImageNet [4]. This dataset has 60000 RGB images from 100 classes and the image resolution is 84 x 84.


### Useful links:
  - [Tutorial about few-shot leanring and meta-learning I](https://www.borealisai.com/en/blog/tutorial-2-few-shot-learning-and-meta-learning-i/)
  - [Tutorial about few-shot leanring and meta-learning II](https://www.borealisai.com/en/blog/tutorial-3-few-shot-learning-and-meta-learning-ii/)


### References
[1] Santoro A, Bartunov S, Botvinick M, et al. One-shot learning with memory-augmented neural networks[J]. arXiv preprint arXiv:1605.06065, 2016.   
[2] Koch, Gregory, Richard Zemel, and Ruslan Salakhutdinov. "Siamese neural networks for one-shot image recognition." ICML Deep Learning Workshop. Vol. 2. 2015.  
[3] Oriol Vinyals, Charles Blundell, Tim Lillicrap, Daan Wierstra, et al. Matching networks for one shot learning. In Advances in Neural Information Processing Systems, pages 3630–3638, 2016.  
[4] Snell, Jake, Kevin Swersky, and Richard Zemel. "Prototypical networks for few-shot learning." Advances in Neural Information Processing Systems. 2017.  
[5] Finn, Chelsea, Pieter Abbeel, and Sergey Levine. "Model-agnostic meta-learning for fast adaptation of deep networks." Proceedings of the 34th International Conference on Machine Learning-Volume 70. JMLR. org, 2017.  
[6] Lake, Brenden, et al. “One shot learning of simple visual concepts.” Proceedings of the Annual Meeting of the Cognitive Science Society. Vol. 33. No. 33. 2011.  
[7] Hoffer, Elad, and Nir Ailon. “Deep metric learning using triplet network.” International Workshop on Similarity-Based Pattern Recognition. Springer, Cham, 2015.
[8] Fei-Fei, Li, Rob Fergus, and Pietro Perona. "One-shot learning of object categories." IEEE transactions on pattern analysis and machine intelligence 28, no. 4 (2006): 594-611.



## 3、One-shot Learning 
One-shot learning is a particular case of few-shot learning when 'shot' $k = 1$.