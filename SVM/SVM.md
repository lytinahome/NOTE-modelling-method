# Support Vector Machine

#### There are three types of SVM:
+ linear SVM with hard margin
+ linear SVM with soft margin
+ non-linear SVM with soft margin

#### the difference between perceptron and SVM:
+ perceptron is any separate hyperplane; SVM is the separate hyperplane with the maximum margin, the solution is unique.
+ perceptron is a linear classifer, the SVM can be non-linear using the kernal trick.

#### related topics:
+ kernal trick.

#### the advantage of SVM
+ the solution is only determined by the support vector. so the solution is stable and is immune to the effect of imbalanced data.


## Linear SVM with hard margin

#### what is the functional margin/ geometric margin/ signed distance?
+ functional margin: y_i(w * x_i + b_i)
+ geomatric margin: y_i(w * x_i + b_i) / ||w||
+ signed distance: correct classified - positive; wrongly classified - negative

#### SVM optimization problem
+ target: min_w, b 1/2 ||w||^2
+ s.t. y_i(w * x_i + b_i) >= 1

on the linear separable dataset, the solution exists and is unique.

#### support vector in SVM - hard margin
the support vector is the data which makes the constrains equal to 0. that's to say, the x_i satisfies y_i(w * x_i + b_i) = 1.
only the support vector will effect the choice of separate hyperplane, the data point other than the support vector won't change the hyperplane. so the solution of the SVM is quite stable.

#### margin in SVM - hard margin
(w * x_i + b_i) = +/-1 is the boundary of the margin. there distance is 2/||w||.

#### the daul problem of SVM - hard margin
TBC

## Linear SVM with soft margin

#### general intro
+ there is a hyperparameter in Linear SVM with soft margin.

#### what is the model?
TBC
note: C is a hyperparameter.

#### what is the dual problem and the algorithm?
TBC 

#### the advantage of solving the dual problem instead of the original problem?
+ it is easier to solve the dual problem than the original problem.
+ it is easy to apply kernal trick to the dual problem.

#### the solution of SVM:
w exists and is unique. In theory b exist but not unique. However, in practice, b is always unique.

#### support vector in SVM - soft margin
when a* > 0, they are support vector:
+ when a* < C, we have $\xi$ = 0. the data is the sv on the margin.
+ when a* = C,
  - when 0 < $\xi$ < 1, the data is the sv between two boundary.
  - when $\xi$ = 1, the data is the sv on the hyperplane.
  - when $\xi$ > 1, the data is mislabeled.

#### margin in SVM - soft margin
(w * x_i + b_i) = +/-1 is the boundary of the margin. there distance is 2/||w||.

### Another way to interpret SVM - soft margin
#### Loss function: Hinge loss founction
sum positive[1 - y_i(w * x_i + b_i)] + \lambda||w||^2

#### the relationship between hinge loss, 0-1 loss and perceptron loss.
TBC



#### Appendix: other version of SVM - soft margin
TBC

