---
title: "Data leakage in ML"
date: 2023-09-23
---
# Data leakage in ML
In this blog post, we will delve into what data leakage is, why it is a critical problem in ML, and explore methods to prevent data leakage. I have decided to write this post after inspecting the source code of various ML pre-processing pipelines online, many of which did not account for data leakage in their design. Despite being a fundamental issue with various preventive approaches, data leakage will become ever more talked as the concern of trustworthiness in machine learning systems grows. I hope that this post will draw some attention among readers.

## What is Data Leakage?

Data leakage in machine learning refers to the notion of information transcending the barrier between the training and testing phases of a model, i.e. data from the training set is inadvertantly including in the testing set. A basic example of this would be to include application outcomes (labels) in training data that is supplied to a model that predicts exam performance of students. Consequently, the model learns patterns from features that should not be available during deployment.

## Importance of Addressing Data Leakage

Data leakage can significantly impact the robustness and real-world performance of machine learning models. It introduces 2 key issues:

- Overfitting: a model with leaks can perform exceptionally well on the training data but fails to generalize to new, unseen data. This can lead to a false sense of security about the model's capabilities.

- Inflated evaluation metrics: leakage can also lead to overly optimistic evaluation metrics, as the model is inadvertently exposed to information it should not have access to during testing. This can mislead practitioners into believing the model is more accurate than it truly is.

Considering ML models are relied on for various tasks from stock market prediction to medical diagnosis and everything in between, this false sense of security can have consequential, far-reaching implications on society.

## Preventing Data Leakage

Many strategies exist to disallow data leakage, including:

- Careful feature engineering: it is important to scrutinise features to ensure they do not contain information that would not be available during deployment. For instance, it is recommended to exclude features like future credit scores if predicting the likelihood of individuals defaulting on loans.

- Cross-validation: implementing cross-validation techniques (such as k-fold cross-validation) to assess model performance across multiple training and testing splits. This helps identify if the model consistently performs well or if the performance is contingent on specific data splits.

- [FOR TIME-SERIES DATA] Temporal validation splits: this ensures the training set chronologically precedes the testing set. This simulates real-world applications, where the model is trained on historical data and tested on future data.
