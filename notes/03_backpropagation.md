# Backpropagation

Backpropagation is the algorithm used to train neural networks.
It provides a systematic way to compute how each weight in the network
contributes to the final loss.

At a high level, backpropagation answers one question:
“How should each weight change to reduce the error?”

## Intuition Behind Backpropagation

A neural network makes a prediction using its current weights.
The loss function measures how wrong that prediction is.

Backpropagation works by:
1. Measuring the final error (loss)
2. Tracing that error backward through the network
3. Assigning responsibility for the error to each weight
4. Updating weights to reduce future error

## Why It Is Called Backpropagation

- "Forward pass": inputs move forward to produce a prediction
- "Backward pass": error flows backward to update weights

The error is propagated backward layer by layer.

## Backpropagation and the Chain Rule

Backpropagation is fundamentally an application of the chain rule from calculus.

In a neural network, the loss depends on the output of the network,
and the output depends on the weights through multiple layers.

### Core Idea

If a value depends on another value, which in turn depends on a weight,
then the effect of that weight on the loss can be computed by multiplying
their individual rates of change.

In simple terms:

Change in Loss w.r.t Weight =
(Change in Loss w.r.t Output) × (Change in Output w.r.t Weight)

### What Happens During Backpropagation

During the backward pass, the network computes:
- How much the loss changes with respect to each layer’s output
- How much each weight contributed to that change
- Gradients that indicate the direction to update each weight

These gradients are then used by an optimizer to update the weights.

Backpropagation does not guess how to update weights.
It computes exact gradients using calculus.
