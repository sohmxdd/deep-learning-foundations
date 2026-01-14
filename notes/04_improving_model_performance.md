# Improving Neural Network Performance

As neural networks grow deeper, training becomes harder due to unstable
activations, slow convergence, and gradient-related issues.

This document covers key techniques used to improve training stability
and performance in deep neural networks.

## Batch Normalization

Batch Normalization is a technique that normalizes the activations of a layer
during training.

Instead of allowing activations to grow or shrink uncontrollably,
batch normalization ensures they remain within a stable range.

### Why Batch Normalization Helps

- Reduces internal covariate shift
- Stabilizes gradient flow
- Allows higher learning rates
- Acts as a form of regularization

Batch normalization often leads to faster convergence
and improved generalization.

## Weight Initialization

Weight initialization determines the starting values of a neural network’s parameters.

Poor initialization can cause:
- Vanishing gradients
- Exploding gradients
- Extremely slow training

### Glorot (Xavier) Initialization

Glorot initialization scales weights based on the number of input
and output connections of a layer.

It helps keep the variance of activations consistent across layers,
making it suitable for sigmoid and tanh activations.

### He Initialization

He initialization is designed specifically for ReLU-based networks.

It assigns slightly larger initial weights to compensate
for ReLU units that output zero for half the inputs.

Proper initialization is critical for deep networks to train effectively.

## Optimization Algorithms

Optimizers define how model parameters are updated using computed gradients.

The choice of optimizer significantly affects convergence speed
and training stability.

### SGD with Momentum

Momentum accumulates a moving average of past gradients
to accelerate learning in consistent directions.

Benefits:
- Faster convergence
- Reduced oscillations
- Better navigation of ravines in the loss surface

### RMSProp

RMSProp adapts the learning rate for each parameter individually
by normalizing gradients using a moving average of squared gradients.

It is particularly effective for non-stationary problems.

### RMSProp

RMSProp adapts the learning rate for each parameter individually
by normalizing gradients using a moving average of squared gradients.

It is particularly effective for non-stationary problems.

## Key Takeaways

- Batch normalization stabilizes training
- Proper weight initialization prevents gradient issues
- Optimizers control how efficiently models learn
- Adam is a strong default, but understanding alternatives matters
