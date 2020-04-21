

## Cleaning up incorrectly labeled data

#### Q: Is it worth your while to go in to fix up some of these labels?
It turns out that deep learning algorithms are quite robust to random errors in the training set, while less robust to systematic errors.
There's certainly no harm to going into your training set and be examining the labels and fixing them. 
Sometimes that is worth doing but your effort might be okay even if you don't.

If you're worried about the impact of incorrectly labeled examples on your dev set or test set, 
what they recommend you do is during error analysis to add one extra column so that you can also count up the number of examples where the label Y was incorrect. 

It depends on the error ratio. 
My advice is, if it makes a significant difference to your ability to evaluate algorithms on your dev set, 
then go ahead and spend the time to fix incorrect labels. 
But if it doesn't make a significant difference to your ability to use the dev set to evaluate cost buyers, 
then it might not be the best use of your time.

#### If you decide to go into a dev set and manually re-examine the labels and try to fix up some of the labels, here are a few additional guidelines or principles to consider. 
+ First, I would encourage you to apply whatever process you apply to both your dev and test sets at the same time. 
+ Second, I would urge you to consider examining examples your algorithm got right as well as ones it got wrong. 
+ Finally, if you go into a dev and test data to correct some of the labels there, you may or may not decide to go and apply the same process for the training set. 

#### Other advice:
+ there's also more manual error analysis and more human insight can be contributed to the deep learning .
+ manually look at the examples and do the error analysis.

## Build your first system quickly, then iterate

#### Q:when building a brand new algorithm, how do you pick (prioritize) which of directions to focus on?
+ first quickly set up a dev/test set and metric. deciding where to place your target. if you get it wrong, you can always move it later, but just set up a target somewhere. 
+ then build an initial machine learning system quickly. not overthink or not make your first system too complicated. Find the training set, train it and see. Start to see and understand how well you're doing against your dev/test set and your values and metric. 
+ use bias/variance analysis as well as error analysis, to prioritize the next steps.

## Training and testing on different distributions
Assume you have two datasource, source A: the dataset you care about, source B: the dataset you find can help training.

#### Option1: (bad option) take the all the data and randomly shuffle them into a train, dev, and test set. 
+ The advantage is that now you're training, dev and test sets will all come from the same distribution, so that makes it easier to manage. 
+ But the disadvantage, and this is a huge disadvantage, is that if you look at your dev set, a lot of it will come from the source B, rather than source A.

#### Option2: (good option) make dev and test dataset use the data all from source A.
+ The advantage of this way of splitting up your data into train, dev, and test, is that you're now aiming the target where you want it to be. 
+ The disadvantage, of course, is that now your training distribution is different from your dev and test set distributions. But it turns out that this split of your data into train, dev and test will get you better performance over the long term.
 the remianing question is: should you use all the data you have?
 
## Bias and Variance with mismatched data distributions
the way you analyze bias and variance changes when your training set comes from a different distribution than your dev and test sets.
 
#### the problem with this analysis is that when you went from the training error to the dev error, two things changed at a time. 
+ One is that the algorithm saw data in the training set but not in the dev set. 
+ Two, the distribution of data in the dev set is different. 

in order to tease out these two effects it will be useful to define a new piece of data which we'll call the training-dev set. 
So, this is a new subset of data, which we carve out that should have the same distribution as training sets, 
but you don't explicitly train your model on this. So just as the dev and test set have the same distribution, 
the training set and the training-dev set, also have the same distribution.

compare the training error, the train-dev error and the dev error to perform the bias/variance analysis.

#### whatever algorithm it's learning, it works great on training-dev but it doesn't work well on dev. we call that a data mismatch problem.
| bayes error| train error | train-dev error | dev error | problem type | 
|--|--|--|--|--|
| 0% | 10% | 11% | 20% | bias + data mismatch |
| 0% | 10% | 11% | 12% | bias |
| 0% | 4% | 7% | 6% | bias - the dev data may be easier |

## Addressing data mismatch

what I usually do is carry out manual error analysis and try to understand the differences between the training set and the dev/test sets. 
To avoid overfitting the test set, technically for error analysis, you should manually only look at a dev set and not at the test set.

When you have insight into the nature of the dev set errors, or you have insight into how the dev set may be different or harder than your training set, what you can do is then try to find ways to make the training data more similar. Or, alternatively, try to collect more data similar to your dev and test sets. 

#### So, if your goal is to make the training data more similar to your dev set, what are some things you can do?
One of the techniques you can use is artificial data synthesis. In speech recognition, I've seen artificial data synthesis significantly boost the performance of what were already very good speech recognition system. So, it can work very well. But, if you're using artificial data synthesis, just be cautious and bear in mind whether or not you might be accidentally simulating data only from a tiny subset of the space of all possible examples.

## transfer learning
in transfer learning, you have a sequential process where you learn from task A and then transfer that to task B.
#### termnology:
+ pre training
+ fine tuning

#### when does transfer learning make sense?
+ Task A and B have the same input X.
+ when you have a lot more data for Task A than for Task B. All this is under the assumption that what you really want to do well on is Task B.
+ transfer learning will tend to make more sense if you suspect that low level features from Task A could be helpful for learning Task B.

## multi-task learning
 In multi-task learning, you start off simultaneously, trying to have one neural network do several things at the same time. And then each of these task helps hopefully all of the other task. 
 
####  when does multi-task learning make sense?
+ One is if your training on a set of tasks that could benefit from having shared low-level features. 
+ Second, this is less of a hard and fast rule, so this isn't always true. But what I see from a lot of successful multi-task learning settings is that the amount of data you have for each task is quite similar.

the only times multi-task learning hurts performance compared to training separate neural networks is if your neural network isn't big enough. But if you can train a big enough neural network, then multi-task learning certainly should not or should very rarely hurt performance. And hopefully it will actually help performance compared to if you were training neural networks to do these different tasks in isolation. 

## end-to-end learning
example: speech recognition; face recognization; machine translation; 

Whether to use end-to-end deep learning

#### pros and cons of end-to-end deep learning
+ pro: let the data speak
+ pro: less hand-designing of components needed
+ con: may need large amount of data -- this is the key
+ con: excludes potentially useful hand-designed componenets




  
