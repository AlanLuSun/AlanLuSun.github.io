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
