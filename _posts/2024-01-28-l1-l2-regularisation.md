---
title: "L1 and L2 Regularisation, Explained"
date: 2024-01-28
---

Weight parameters in a neural network can be thought of the importance an input has on the subsequent layers. When overfitting, a lot of trust is placed on a network, in other words, values assigned to weights are high. Thus, keeping them low can prevent overfitting - this is what L1 and L2 regularisation can help us achieve. 

Both approaches include the weight values in the loss calculation, so models are penalised for higher weight values.

## l1 - aka norm or lasso
This method encourages weights to be 0.0, effectively making neurons that rely on these weights disappear - thus connections disappear and the regularised network becomes more sparse. The maths behind this can be summarised as **adding the sum of absolute values of weights to the loss calculation**. Paying attention to absolute values, as weight values may be negative or positive.

## l2 - aka ridge or weight decay
This method also aims for a sparser network, with the difference that **the sum of squared values of weights are added to the loss calculation**. L2 penalises weights that are much higher or lower (if weight < 0) more severely.

## Changes to Loss Landscape
Both the absolute function and square function are convex. Adding the convex regularisation term can result in a more convex loss landscape overall, potentially removing some local optima and denoising the landscape.

## Alpha Parameter of L1/L2 Regularisation
The alpha parameter, a real value between 0 and 1, allows us to configure how much attention to pay when penalising weights:
- low alpha: not much attention paid (less likely to penalise), model will be allowed to overfit.
- high alpha: model will underestimate the weights and underfit the problem.

## Applying L1/L2 Regularisation
- L1/L2 can work with all network types and are supported by many libraries including Tensorflow and Keras.
- Both approaches require normalised input data.
- It is possible to use L1 and L2 together.
