---
title: 'PointNet:Deep Learning on Point Sets for 3D Classification and Segmentation'
date: 2018-06-25
permalink: /posts/2018/06/PointNet/
tags:
  - machine learning
---
An introduction to PointNet
[original paper](https://arxiv.org/abs/1612.00593)


Properties of Points Sets
======
1. Unordered.
Point cloud is a set of points without specific order. In orther words, a network that consumes N 3D point sets needs to be invariant to N! permutations of the input set in data feeding order.

1. Interaction among points.
The points are from a space with a distance metric. It means that points are not isolated, and neighboring points from a meaningful subset. Therefore, the model needs to be able to capture local structures from nearby points, and the combinatorial interactions among local structures.

1. Invariance under transformations. 
As a geometric object, the learned representation of the point set should be invariant to certain transformations. For example, rotating and tanslating points all together should not modify the global point cloud category not the segmentation of the points.

Pointnet Architecture
======
![Pointnet Architecture](/images/pointnet-architecture.png)

Symmetry Function for Unordered Input
------
Geberally speaking, there are three ways to make a model invariant to input permutaion.
1. sort input into a canonical order 
1. treat the input as a sequence to train an RNN, but augment the training data by all kinds of permutations
1. use a simple symmetric function to aggregate the information from each point. Here, a symetric function takes n vectors as input and outputs a new vector that is invariant to the input order.

![symmetry function](/images/symetry-function.png)

Local and Global Information Aggregation
------
1. classification
It can easily train a SVM or multi-layer perceptron classifier on the shape global features for classification. 

1. point segmentation need a combination of local and global knowledge.
Achieve: After computing the global point features by concatenating the global feature with each of the point features. Then we extract new per point features based on the combined point features - this time the per point feature is aware of both the local and global information.

With this modification this network is able to predict per point quantities that rely on both local geometry and global semantics. 

Joint Alignment Network
------
The semantic labeling of a point cloud has to be invariant if the point cloud undergoes certain geometric transformations, such as rigid transforma- tion. We therefore expect that the learnt representation by our point set is invariant to these transformations.

