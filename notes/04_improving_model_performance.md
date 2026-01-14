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
