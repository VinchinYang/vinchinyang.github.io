---
title: 'Frustum PointNets for 3D Object Detection from RGB-D Data'
date: 2018-06-25
permalink: /posts/2018/06/FPointNet/
tags:
  - machine learning
---
An introduction to Frustum PointNet
[original paper](https://arxiv.org/abs/1711.08488)


Introduction
======
3D sesor data is often in the form of point clouds. And how to represent point cloud and what deep net architecture to use for 3D object detection.remains an open problem. 

Most exiting works convert 3D points clouds to images by projection or to volumetric grids by quantization and then apply convolution networks.

However, this data representation transformation may obscure natural 3D patterns and invariances of the data. Recently, a number of papers have proposed to process point clouds directly without converting them to other formats. For exampel Pointnets.

While Pointnets are capable of claasifying a whole point cloud, it is unclear how this architecture can be used for instance-level 3D object detection 

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

