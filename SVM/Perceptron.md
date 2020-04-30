# Perceptron

#### Basic property of perceptron:

+ Perceptron is a discriminative model.
+ the solution of perceptron algorithm is not unique.
+ perceptron is a linear model.
+ perceptron only works for the linear separable dataset. when the dataset is not linear separable, the solution will oscillate.
+ perceptron is closely related to SVM.
+ perceptron can be deemed as the foundation of the neural network.

#### the format of perceptron model
f(x) = sign(w*x + b)

#### the loss function of perceptron
Two options: will use second one.

1. accurate rate, 0-1 loss function, not differentiable.
2. mislabled point to the hyperplane: L(w, b) = - sum(y_i * (w * x_i + b_i)) when x_i is miscalssified.

#### How to optimize the loss function

use the stochastic gradient descent.
when the dataset is linear separatable, the algorithm will converge; when the dataset is not linear separable, the solution will oscillate.

