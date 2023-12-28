---
title: "The Unstable Gradient Problem"
date: 2023-12-28
---

## Unstable Gradients and Backpropagation

Backpropagation enables models to learn patterns from data; weights are updated in proportion to the error measured after each epoch of training. However, this process of learning is not always this straightforward, as we will see in this article which discusses the unstable gradient problem and some potential solutions.

To understand the unstable gradient problem, it is crucial to look at backpropoagation algorithm and its use of the chain rule. The chain rule allows us to decompose the derivative of a composite function into the product of the derivatives of its individual functions. In the context of neural networks, the chain rule is applied iteratively across the layers during backpropagation. The problem emerges when many gradients are multiplied across numerous layers.

The unstable gradient problem exists in two forms:
  - vanishing gradient problem
  - exploding gradient problem

### Vanishing Gradients
If the majority of these gradients are small, i.e. < 1, the product of these small values tends toward zero, causing the vanishing gradient problem.

### Exploding Gradients
Conversely, if some gradients are large, the resulting product can increase exponentially, resulting in the exploding gradient problem.

## Potential Solutions
### Adopt a New Weight Initialisation Method
Techniques like He initialisation or Xavier initialisation set the initial weights in a way that prevents gradients from becoming too small or too large. By initialising weights with a set mean and variance that is proportional to the number of input units (and in case of Xavier's technique the output units as well) gradients are prevented from becoming too small or too large.
### Use Non-Saturating Activation Functions
Activation functions introduce non-linearity to the neural network, allowing it to learn complex relationships in the data. However, some activation functions have saturation regions where the gradient approaches zero (vanishing gradient problem) or becomes extremely large (exploding gradient problem). If we remember the chain rule, we can get unstable gradients when multiplying these very large or very small values. If you wish to take a look at various non-linear (and some basic linear) activation functions, I have written a post [here](https://senertopaloglu.github.io/blog/2023/10/29/activation-functions.html).
### Batch Normalisation
Batch normalisation is a technique that normalises the inputs of each layer to have zero mean and unit variance. This helps in stabilising the distribution of activations throughout the network, reducing the likelihood of exploding or vanishing gradients. I have also talked about this in a [previous post](https://senertopaloglu.github.io/blog/2023/11/21/batch-size-and-batch-normalization.html).
### Gradient Clipping
Gradient clipping involves setting a threshold for the gradients during the training process. If the gradient of a parameter exceeds this threshold, it is scaled down to ensure that its magnitude does not surpass the specified limit. The threshold can be a fixed value or dynamically adjusted based on the global norm of all gradients. If the global norm of the gradients exceeds the threshold, all gradients are scaled down proportionally to ensure that the global norm does not exceed the specified limit.
