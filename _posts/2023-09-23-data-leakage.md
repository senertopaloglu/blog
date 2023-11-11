---
title: "Data leakage in ML"
date: 2023-09-23
---
# Data leakage in ML
In this blog post, we will delve into what data leakage is, why it is crucial in the context of ML, and explore methods to combat it. I have decided to write this post after inspecting the source code of various ML pipelines online, a significant amount of which did not account for data leakage. Despite being a fundamental issue with various preventive approaches, data leakage will become ever more talked as the concern of trustworthiness in machine learning systems grows. I hope that this post will draw some attention among readers.

## What is Data Leakage?

Data leakage in machine learning refers to the notion of information transcending the barrier between the training and testing phases of a model - data from the training set is inadvertantly including in the testing set. Consequently, the model learns patterns from features that would not be available during deployment.

## Importance of Addressing Data Leakage

Data leakage can significantly impact the robustness and real-world performance of machine learning models. It introduces 2 key issues:

- Overfitting: a model with leaks can perform exceptionally well on the training data but fails to generalize to new, unseen data. This can lead to a false sense of security about the model's capabilities.

- Inflated evaluation metrics: leakage can also lead to overly optimistic evaluation metrics, as the model is inadvertently exposed to information it should not have access to during testing. This can mislead practitioners into believing the model is more accurate than it truly is.

Considering models that models can (and already have been) relied on for various tasks, including stock market prediction and medical diagnosis, this false sense of security can have consequential, far-reaching implications on society.

## Preventing Data Leakage

Many strategies exist to combat data leakage, including:

- Feature Engineering: Scrutinize features to ensure they do not contain information that would not be available during deployment. For instance, if predicting loan defaults, exclude features like future credit scores.

- Cross-validation: Implement cross-validation techniques such as k-fold cross-validation to assess model performance across multiple training and testing splits. This helps identify if the model consistently performs well or if the performance is contingent on specific data splits.

- [FOR TIME-SERIES DATA] Temporal Validation Splits: In time-series data, use temporal validation splits to ensure that the training set precedes the testing set chronologically. This simulates the real-world scenario where the model is trained on historical data and tested on future data.
