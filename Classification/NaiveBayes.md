# Naive Bayes

Naive Bayes is a generative model. it can estimate the joint distribution of X and Y, P(X, Y).

#### the assumption used in NB
the features are independent given fixed Y. However, in practice, rare data can meet this assumption.

#### maximize MAP = minimize loss expectation (0-1 loss function)

#### NB uses frequency to estimate the conditional probability; to avoid the 0 cases, it utilizes the trick "Laplacian smoothing" -- that is to add a positive number \lambda (usually \lambda = 1) to every frequency.

#### if we assume there is dependency between features, it becomes Bayes network.


