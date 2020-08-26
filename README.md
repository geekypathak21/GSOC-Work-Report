<p align="center">
  <img width="556" height="112" src="https://github.com/himanshupathak21061998/GSOC-Work-Report/blob/master/src/logo.png">
</p>

#### Organisation: [mlpack](https://github.com/mlpack)

#### Project: Implementing Essential Deep Learning Modules

#### Mentor: [Saksham Bansal](https://github.com/saksham189)

## Abstract
This summer I was selected as a student developer for Google Summer of Code under mlpack. This report summarises all the work that I have done during the span of 3 months as a project "Implementing Essential Deep Learning Modules"
mlpack is an open-source machine learning C++ library which aims to provide fast, extensible implementations of cutting-edge machine learning algorithms. This project focused on adding some useful machine learning modules which were not currently present in the mlpack library.

## Goal
This project mainly focused on adding three different deep-learning modules.

- **Radial Basis Function Network (RBFN)**

RBFN is an artificial neural network which uses Radial Basis Function as an activation function. It is a three-layer feedforward neural network. The first layer corresponds to the inputs of the network, the second is a hidden layer consisting of a number of RBF non-linear activation units, and the last one corresponds to the final output of the network. Activation functions in RBFNs are conventionally implemented as Gaussian functions. For more information read [this paper](http://proceedings.mlr.press/v51/que16.pdf).

- **Kernel Support Vector Machine**

Kernel SVM are the support vector machines which use non-linear kernel functions to train. We can use various kernels like Gaussian, Polynomial and Linear etc. To get more information read [this paper](https://www.ijrte.org/wp-content/uploads/papers/v7i5s4/E10010275S419.pdf)

- **Deep Belief Network(DBN)**

It is a generative graphical model or a deep neural network composed of multiple layers of latent variables ("hidden units"), with connections between the layers but not between units within each layer.
A DBN can reconstruct input as well as can be used for classification. For more information read [this paper](http://www.cs.toronto.edu/~hinton/absps/fastnc.pdf).

## Results
Most part of the project is complete but some parts are left:-

- **Radial Basis Function Network (RBFN)**

Implementation of RBFN is pretty much complete and merged. So, the implementation was quite simple. I added an RBF layer which can be used with FFN class and also added some activation function which can be with RBF layer.

[Radial Basis Function Layer](https://github.com/mlpack/mlpack/pull/2261) (merged)

[Activation Functions for RBF Layer](https://github.com/mlpack/mlpack/pull/2424) (merged)


- **Kernel Support Vector Machine**

I used a sequential minimal optimization algorithm to implement the `KernelSVM` . We already had various kernels implemented in mlpack with no requirement to add more. We can optimize any non-linear kernel using `SMO` algorithm. Also after implementing the `SMO` algorithm for multi-class classification I used a one-vs-one approach.

[Kernel SVM](https://github.com/mlpack/mlpack/pull/2456) (open)

- **Deep Belief Network(DBN)**

In implementation of `DBN` I created a DBN class which can be used to stack various `RBM`. The `DBN` is trained by a greedy approach to train each `RBM` layer statically and pass the output from trained layer to next layer and train that using those output.

[Deep Belief Network](https://github.com/mlpack/mlpack/pull/2555) (open)



<p align="center">
  <img width="366" height="191" src="https://github.com/himanshupathak21061998/GSOC-Work-Report/blob/master/src/contributions.png">
</p>


## Conclusion
I would still like to contribute to mlpack after completing the GSOC. I enjoyed a lot while contributing to mlpack and learned various things. It's been an exciting journey of three months.
I have to complete various tasks related to my project such as adding CLI binding for `KernelSVM` and optimize the code of smo algorithm and compare it to `sklearn` library and adding some tests for `DBN`.


## Acknowledgments
I would like to thank my mentor Saksham Bansal and everyone else in the mlpack community. I can't be able to complete the project without the help of you guys. Saksham helped me a lot and gave timely reviews on 
my pr's and also Ryan and Marcus helped me a lot and gave me very helpful suggestions to develop this project.mlpack is a good library to learn machine learning with c++ it helps to understand implementation of various machine learning algorithms.

Thanks Google for sponsoring such events and promoting the open-source community.
