# Convolutional Neural Networks


## Edge detection
using Convolution to detect the edge in the pic

## Padding

#### why padding?
- avoid shrinking in dimension everytime applying a convolution operator
- the pixel at the corner or the edge is only touched fewer times than the rest

#### name the common used padding
- same convolution/padding: keep the size
- valid convolution/padding: no padding

#### why usually use odd numbered filters?
- even numbered filters leads to asymmetric padding
- odd numbered filter is easy to define the central position, which often used to refer the location of the filter.

## Stride

## Pooling

#### name two common used pooling?
- max pooling
- average pooling

#### there is no parameter used in pooling, so no derivation needs to be calculated in this step.

## Full-connection Layer

## Why Convolutions?

#### there are two main advantages of convolution layers over just using fully connected layers.

+ parameter sharing 
+ sparsity of connections

# Case Study

## Classic models

+ LeNet-5
+ AlexNet
+ VGGNet

## ResNet

#### what is ResNet?

#### The advantage of ResNet?

## 1 * 1 Convolutions

#### What is the advantage of 1 * 1 convolutions?

## Inception Network

#### what is the tricks used in inception network?
+ 1 * 1 convolutions
+ different filters in one layer
+ use intermediate layer to do prediction

# Practical advice for using ConvNets
## Using Open-source Implementation

## Transfer Learning
build your model on top of others' model

#### how to implement transfer learning?

## Data Augmentation
There is hyper-parameters needs to be set in data augmentation.
You can borrow other open-source data augmentation methods as well.

#### name common used data augmentation methods?
+ mirroring 
+ randomly cropping
+ color shifting
+ PCA color augmentation
+ rotation
+ shearing of the image
+ local warping

## State of computer vision

we are lack of data in CV problem. That is why we need to rely on hand-engineering a lot.

#### The tips for doing well on benchmarks
+ ensembling
+ multi-crop at test time

#### principle to use open source code
+ use architecture of networks published in literature
+ use open source implementations if possible
+ use pretrained models and fine-tune on your dataset

