# Outlier Detection through Null Space Analysis of Neural Networks

This project implements the outlier detection method described in the paper ["Outlier Detection through Null Space Analysis of Neural Networks"](https://arxiv.org/pdf/2007.01263.pdf) by Matthew Cook, Alina Zare, Paul Gader. The method is based on leveraging the null space of neural networks to detect outliers in high-dimensional data.


### Paper Overview

Many machine learning algorithms encounter difficulties in detecting outlier data points (data points that differ from other training data and essentially have a different distribution function) and noise. The ability to detect these data points is crucial. In previous works, two separate models were trained for this task: one model for classifying data points and another model for detecting outliers. The problem with these methods is their high complexity because two separate models are trained. However, in the method proposed in the paper "Outlier Detection through Null Space Analysis of Neural Networks," a single model is trained for both tasks. In this paper, we use the null space of the weight matrices in each layer of the neural network to detect these data points.

Null space of a matrix is defined as: 


$N(A) = \[\{z \in \mathbb{R}^n \ | \ Az = 0\}\]$

where 
- A is a linear mapping. In other words, the null space of matrix $A$ defines the region of the input space that maps to zero.


In each layer of a neural network, there is a matrix multiplication followed by passing through an activation function. Each of these weight matrices has a null space, some of which may be empty. However, any weight matrix that has more inputs than outputs has a non-empty null space. Most deep learning models also have this property, meaning that the number of inputs to them is greater than their outputs.

In order to accomplish this, we define the Null Space Analysis (NuSA) Term which computes the magnitude of the
projecting onto the span of the column space: 

$NuSA = \frac{\left\|P(W) \cdot x\right\|}{\left\|x\right\|}$
 
$P(W) = C(W)^T C(W)$
where
- $x$ is the input
- $W$ is the weight matrix of the neural network
- $C(W)$ represents the column space basis of the matrix $W$

We can encode the outlier detection into a network by directly incorporating the NuSA
calculation into the loss function used for training: 
$NuSA = \lambda \sum_{l \in L} \frac{\left\|P(W_l) \cdot x_l\right\|}{\left\|x_l\right\|}$

For more details about the paper, please read the [original paper](https://arxiv.org/pdf/2007.01263.pdf).
### Dataset
The dataset used for this paper is CIFAR-10, which is an established computer vision dataset used for object recognition. It is a subset of the 80 million tiny images dataset and consists of 60,000 32x32 color images containing one of 10 object classes, with 6000 images per class. It was collected by Alex Krizhevsky, Vinod Nair, and Geoffrey Hinton. You can find the dataset [here](https://www.kaggle.com/c/cifar-10/).

### Results 
The result of the implementation is a comparison of classification performance with and without NuSA. All hyperparameters are set as described in the paper.

<center>

![Capture](https://github.com/MohammadAmini1998/Advanced-Data-Mining-Project/assets/49214384/f5214ff9-f8f4-43dc-a377-bd4264a8f047)

</center>


## Contributions and Feedback

I welcome contributions, feedback, and suggestions for improvement! If you have any ideas, questions, or insights regarding this project, feel free to reach out and engage in discussions.

Let's continue exploring the exciting possibilities of Machine Learning together! 🚀

By the way, If you find this project helpful or interesting, please star the repository to show your support! <img src="https://github.com/MohammadAmini1998/MohammadAmini1998/assets/49214384/51261e26-5869-4450-bf43-8f19aacce80d" alt="512" width="50" height="50">













