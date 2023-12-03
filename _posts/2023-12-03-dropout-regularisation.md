# Dropout Regularisation
Dropout is a technique where randomly selected neurons are ignored (dropped out) during each iteration of training. This means that their contribution to the activation of downstream neurons is removed on the forward pass, and any weight updates are not applied to the neuron on the backward pass. 

As a neural network learns, neuron weights settle into their context within the network. Weights of neurons are tuned for specific features, providing some specialization. Neighboring neurons come to rely on this specialization, which, if taken too far, can result in a fragile model that has effectively specialized for the training data. Such models fail to generalize effectively to new, unseen data (termed overfitting in the space of machine learning/deep learing). 

By introducing dropout, the network is less likely to memorize the training data and is encouraged to learn more general patterns. During testing, all neurons are typically used, but their weights are scaled to account for the dropout probability used during training. It is important to (randomly) select a different subset of neurons to be dropped at each iteration to prevent co-adaptation; if the same set of neurons were dropped out consistently during training, the network might develop strong dependencies between certain neurons, random dropout disrupts these dependencies.

Dropout is just one of many regularization techniques, and it can be said that there is no one size fits all approach. Other regularization methods include L1 or L2 regularization, which I intend to discuss in a future post. 

For further information on this topic, I recommend taking a look at [“Dropout: A Simple Way to Prevent Neural Networks from Overfitting”](https://jmlr.org/papers/v15/srivastava14a.html) by Srivastava et al.
