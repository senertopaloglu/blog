---
title: "Exploring Activation Functions in Machine Learning"
date: 2023-10-29
---
# Exploring Activation Functions in Machine Learning

## Introduction

Activation functions are essential components in artificial neural networks, playing a crucial role in enabling these networks to model complex relationships and make predictions. They introduce non-linearity to the network, allowing it to learn and approximate a wide range of functions. In this blog post, we'll delve into the world of activation functions, exploring their types, characteristics, and use cases in machine learning.

## What Are Activation Functions?

In the context of neural networks, activation functions are mathematical functions applied to the output of each neuron, introducing non-linearity into the network. This non-linearity is vital for enabling the network to approximate complex functions and learn from data. Without activation functions, a neural network would simply be a series of linear transformations, making it incapable of modeling non-linear relationships.

## Types of Activation Functions

### Step Function
The step function, also known as the Heaviside step function, is a simple binary activation. It assigns 1 to input values greater than a certain threshold and 0 otherwise. While rarely used in modern deep learning, it was foundational in the history of artificial neurons.
![step function](https://github.com/senertopaloglu/blog/blob/main/_posts/resources/step-function.PNG)

### Sigmoid Function:
The sigmoid function is a smooth, S-shaped curve that maps any input value to a range between 0 and 1. It was widely used in the past but has fallen out of favor in favor of other functions due to the vanishing gradient problem.
![Sigmoid function](https://github.com/senertopaloglu/blog/blob/main/_posts/resources/sigmoid-function.PNG)

### Hyperbolic Tangent (tanh) Function:
Similar to the sigmoid function, the hyperbolic tangent function squashes input values to a range between -1 and 1. It overcomes some of the issues associated with the sigmoid function, and holds the following advantages:

- tanh function maps input values to the range [-1, 1], with the center point at 0, unlike the sigmoid function, whose center point is at 0.5. This helps in addressing the vanishing gradient problem, especially in scenarios where the activations tend to drift towards one extreme.
- It has a steeper gradient than the sigmoid function in the region around 0. This means that the gradients during backpropagation are stronger, facilitating more effective weight updates. Stronger gradients can lead to faster convergence during training.
![tanh function](https://github.com/senertopaloglu/blog/blob/main/_posts/resources/tanh-function.PNG)

### Rectified Linear Unit (ReLU):
ReLU is one of the most popular activation functions in modern deep learning. It replaces all negative values with zero while leaving positive values unchanged. This function is computationally efficient and has been found to work well in many applications.
![RELU function](https://github.com/senertopaloglu/blog/blob/main/_posts/resources/relu-function.PNG)

### Leaky ReLU:
Leaky ReLU is a variation of the ReLU function that allows a small gradient for negative values. This modification helps address the "dying ReLU" problem, where neurons can get stuck during training.
![Leaky-RELU function](https://github.com/senertopaloglu/blog/blob/main/_posts/resources/leaky-relu-function.PNG)
