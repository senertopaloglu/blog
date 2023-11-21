---
title: "Batch Size and Batch Normalisation"
date: 2023-11-21
---
## Mini-Batches and their Importance in Training
During a training epoch we feed our network, calculate the errors and update the weights in the network accordingly. It's not practical to update our network weights only once per epoch after looking at the error produced by all training samples. Instead, we can take a mini-batch (subset) of training samples. For example, if the training set at hand for a CNN has 12 images and we declare a batch size of 4, then weights will be updated 3 times.

### Advantages of using Mini-Batches
- Networks tend to train faster with mini-batches since weights are updated more often
- By dividing data sets we reduce the amount of training data that must be kept in RAM at any time, particularly important for large data sets and machines with low memory capacity
- Also, the noise produced by a small batch-size can help escape local minima

**If mini-batches are used, it is advised to increase the number of training epochs and experiment with different batch sizes to find an optimal value**

## Model Input Normalisation and Batch Normalisation
While utilising mini batches is in training stage, normalisation is a method of pre-processing data - especially when features have different scales (varying ranges). One of the most common ways to normalise data is to subtract its mean value and divide by the standard deviation. This leaves everything centered around 0 with a standard deviation of 1. It is good practice to normalise model inputs - this avoids problems with activation functions and gradients.

Going back to the topic of this post, batch normalisation is important because:
Deeper layers are trained based on previous layer outputs and weights get updated via gradient descent, as a result there is a point where layers no longer benefit from normalisation and they need to adapt to previous layers' weight changes, exacerbating the issue of learning their own weights. 

Batch normalisation makes sure that, independently of the changes, the inputs to the next layers are normalized. To optimise this process, there are trainable parameters that learn how much of this normalisation is kept by scaling or shifting it.

### Advantages of Batch Normalisation
- Improves gradient flow
- Reduces weight initialisations dependence
- Limits internal covariate shift (basically a layer's dependence on the previous layer's outputs when learning its weights)
