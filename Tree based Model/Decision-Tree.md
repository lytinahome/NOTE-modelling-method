# Decision Tree

#### What need to learn when developing a decision tree?
+ the shape of the tree (very hard --> Greedy Algorithm)
+ split threshold
+ value in each leaf 

#### how to choose the best decision tree?
+ has exponential number of candicates
+ greedy algorithm -- to optimize the uncertainty: using Entrogy or Mutual information.
+ select the features


#### when to stop splitting?
+ to avoid overfitting
+ set the maximum depth
+ set minimum leaf sample
+ rely on cross validation


#### gini and entropy
1. Gini’s maximum impurity is 0.5 and maximum purity is 0 
2. Entropy’s maximum impurity is 1 and maximum purity is 0
3. Different decision tree algorithms utilize different impurity metrics: CART uses Gini; ID3 and C4.5 use Entropy. This is worth looking into before you use decision trees /random forests in your model.
