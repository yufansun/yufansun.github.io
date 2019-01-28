---
layout: post
title:  "Parallel Computing in Neural Networks"
date:   2019-01-27 17:30:17 -0400
categories: Parallel Computing
author: Yufan Sun
---
## Bio
I’m a first year graduate student in Electrical Engineering and Computer Science department.  My research interests lie in the area of computer vision and machine learning. From the class, I want to learn the concepts of parallel computing and how to write programs that run in parallel to solve challenging problems in machine learning. 

## Application
With the increase of computing power, deep neural networks have regained it’s popularity. Neural networks are good at clustering and classification and it’s widely used in computer vision, speech recognition, machine translation and so on. The training for each node in a neural network is time-consuming and it has become the bottleneck of training performance. However, the computations for each node are generally independent of other nodes, so parallel computing can be applied here. It turned out that the parallel training algorithm runs 63 times faster than its sequential version.

There are two main approaches of parallelization. One is model parallelism, where different machines are responsible for different steps of a single network. Model parallelism is good for scalability and large models, but it doesn’t perform well for implementation, fault tolerance and cluster utilization. The other approach is data parallelism. In this approach, each worker machine process different subset of the training data, and then the results are combined and synchronized together. Different implementation details can be chosen such as parameter averaging/ update-based approaches; synchronous/asynchronous methods; centralized/distributed synchronization.

There is no best distributed neural network training approach because of different criteria we may use. Performance also depends on other factors such as the size and type of the network which varies for each task. In fact, parallel computing isn’t always the best option when training a neural network. Firstly, it has an overhead compared to running in a single machine. Secondly, the setup time and hyperparameter tuning is more complex than traditional training methods. In general, distributed computing is preferable when the ratio of transfers to computation is low.

## Reference
1. Sierra-Canto, Xavier, et al. “Parallel Training of a Back-Propagation Neural Network Using CUDA.” *2010 Ninth International Conference on Machine Learning and Applications*, 2010, doi:10.1109/icmla.2010.52.
1. Skymind. “Introduction to Distributed Training of Neural Networks.” *Deep Learning for Enterprise*, Deep Learning for Enterprise, 2 Mar. 2018, blog.skymind.ai/distributed-deep-learning-part-1-an-introduction-to-distributed-training-of-neural-networks/.
