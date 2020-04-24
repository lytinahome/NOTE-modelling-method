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

#### there are two main advantages of convolutional layers over just using fully connected layers.

+ parameter sharing 
+ sparsity of connections
