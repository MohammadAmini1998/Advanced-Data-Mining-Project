# Outlier Detection through Null Space Analysis of Neural Networks

This project implements the outlier detection method described in the paper "Outlier Detection through Null Space Analysis of Neural Networks" by Bremer et al. The method is based on leveraging the null space of neural networks to detect outliers in high-dimensional data.

### Paper Overview

Many machine learning algorithms encounter difficulties in detecting outlier data points (data points that differ from other training data and essentially have a different distribution function) and noise. The ability to detect these data points is crucial. In previous works, two separate models were trained for this task: one model for classifying data points and another model for detecting outliers. The problem with these methods is their high complexity because two separate models are trained. However, in the method proposed in the paper "Outlier Detection through Null Space Analysis of Neural Networks," a single model is trained for both tasks. In this paper, we use the null space of the weight matrices in each layer of the neural network to detect these data points.

Null space of a matrix is defined as: 
$N(A) = \{z \in \mathbb{R}^n | Az = 0\}$





