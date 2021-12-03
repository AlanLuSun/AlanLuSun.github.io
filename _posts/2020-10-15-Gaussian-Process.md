---
title: Gaussian Process
date: 2020-10-15
permalink: /posts/2020-10-15-Gaussian-Process/
excerpt: Using Gaussian Process for prediction
tags:
  - Learning Notes
---

# Gaussian Process  
*Author: Changsheng Lu (卢长胜)*

## Definition
Gaussian process (GP) is a set of random variables following Gaussian distribution.  

## Gaussian process for machine learning  
Essentially, it uses the correlation between training data and test data to model the prediction of test data, and each prediction is subject to a Gaussian distribution.  
- Tutorial can be found [here](https://katbailey.github.io/post/gaussian-processes-for-dummies/) 

## Algorithm
Before introducing the algorithm, we first define the squared exponential kernel $k$:

$$
k(A, B) = e^{-\frac{1}{2p}(a \ominus b)}= \left[ \begin{matrix}
  e^{-\frac{1}{2p}{\|a_1 - b_1\|}^2} & e^{-\frac{1}{2p}{\|a_1 - b_2\|}^2} & \cdots & e^{-\frac{1}{2p}{\|a_1 - b_n\|}^2} \\
  e^{-\frac{1}{2p}{\|a_2 - b_1\|}^2} & e^{-\frac{1}{2p}{\|a_2 - b_2\|}^2} & \cdots & e^{-\frac{1}{2p}{\|a_2 - b_n\|}^2} \\
  \cdots        & \cdots        & \cdots & \cdots        \\
  e^{-\frac{1}{2p}{\|a_m - b_1\|}^2} & e^{-\frac{1}{2p}{\|a_m - b_2\|}^2} & \cdots & e^{-\frac{1}{2p}{\|a_m - b_n\|}^2} 
\end{matrix} \right]
$$

where $A$ has $m$ data points and $B$ has $n$ data points, and each element $k_{ij}$ ranges from 0~1.  

Assuming the training set is $\{X_1, Y_1\}$ and testing set is $X_2$, now our task is to predict the label $\hat{Y_2}$ of $X_2$. The prediction value of each data can be modeled to satisfy the Gaussian distribution according to Gaussian process, which can be formulated as:

$$
\left(\begin{matrix}
  f \\ f_s
\end{matrix}\right)
\sim 
\mathcal{N}\left( \left(\begin{matrix} \mu \\ \mu_s\end{matrix}\right), \left(\begin{matrix} K & K_s \\ K^\text{T}_s & K_{ss}\end{matrix}\right) \right)
$$  

**The overall algorithm is as follows:**  
**Step 1:** compute variance $K_{ss}$ for testing data, $K_{ss} = e^{-\frac{1}{2p}(X_2 \ominus X_2)}$, with the size of $N \times N$.  
**Step 2:** (optional) compute prior

$$L_{ss}L^{\text{T}}_{ss} = K_{ss}$$

$$f_{prior} = \mu_s + L_{ss}\mathcal{N}(0, I)$$

where $L_{ss}$ can be obtained using Cholesky decomposition and $\mu_s$ is unknown so far (however we can assume to be zero here to visualize the $f_{prior}$). $f_{prior}$ has the size of $N \times 1$.  
**Step 3:** compute variance $K$ for training data, $K = e^{-\frac{1}{2p}(X_1 \ominus X_1)}$, with the size of $M \times M$.

$$LL^{\text{T}} = K$$

So that $L = CholeskyDecom(K)$, with the size of $M \times M$.  
**Step 4:** compute covariance between training data and testing data $K_s$, $K_s = e^{-\frac{1}{2p}(X_1 \ominus X_2)}$, with the size of $M \times N$. 

$$LL_{s} = K_s$$

We can obtain $L_{s}=linearSolve(L, K_s)$, with the size of $M \times N$.  
**Step 5:** compute the mean at test points

$$LL'=y$$

$$\mu_s = L^{\text{T}}_sL'$$

where $\mu_s$ has the size of $N \times 1$.  
**Step 6:** compute the posterior

$$L'_{ss}L'^{\text{T}}_{ss} = K_{ss}-L^{\text{T}}_sL_{s}$$

So that $L'_{ss}=CholeskyDecom(K_{ss}-L^{\text{T}}_{s}L_{s})$, with the size of $N\times N$. The posterior function is

$$f_{post} = \mu_s + L'_{ss}\mathcal{N}(0, I)$$

The standard deviation can be computed by

$$s2=diag(K_{ss}) - diag(L^{\text{T}}_sL_s)=diag(K_{ss}-L^{\text{T}}_sL_{s})$$  

$$stdv = sqrt(s2)$$

$diag(.)$ means utilizing the diagnal elements to form a vector so that $s2$ has the size of $N \times 1$. $stdv$ is the computed standard diviation. The oscillation range of posterior function can be written as

$$\mu_s \pm j*stdv$$

For example, $\mu_{s}{\pm}1*stdv$, $\mu_{s}{\pm}2*stdv$, $\mu_{s}{\pm}3*stdv$, etc.





