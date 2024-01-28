# L1 and L2 Regularisation, Explained

keeps weights low in neural network. why do this? weight can be thought of the importance an input has on the subsequent layers of a neural net. When overfitting, a lot of trust is placed on a network - weights are high. Thus, keeping them low can prevent overfitting.

How? add the weights in the loss calculation, this means that the model is penalised for higher weight values. the way this is done differs between l1 and l2.

## l1 - aka norm or lasso
this method encourages weights to be 0.0, effectively making neurons that rely on these weights disappear - thus connections disappear and the regularised network becomes more sparse. the maths behind this can be summarised as; **adding the sum of absolute values of the weights to the loss** why absolute values? because weights may be negative or positive.

## l2 - aka ridge or weight decay
same as l1, but adds sum of the **squared** values of the weights to the loss. this penalises weights higher or lower weights (if negative) more severely. this results in less sparse weights.

## Changes to Loss Landscape
Both the absolute function and square function are convex. Adding the convex regularisation term can result in a more convex loss landscape overall.

## Alpha Parameter of L1/L2 Regularisation
both methods have a parameter, alpha, that allows us to configure how much attention to pay to penalty. Alpha is a real value between 0 and 1.
low alpha: model will be allowed to overfit, not much attention paid.
high alpha: model will underestimate the weights and underfit the problem.

l1/l2 can work with all network types and are supported by many libraries including (tf?, pytorch?, keras?).
l1/l2 requires normalised inputs (I have a post on this).
can use l1+l2 together - explain the effect of this.



link to how l1/l2 changes loss landscape.
