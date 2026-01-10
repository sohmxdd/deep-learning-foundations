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

## Why Backpropagation Works Efficiently

Backpropagation is computationally efficient because it reuses intermediate
results computed during the forward pass.

Each layer only needs local information:
- Its input
- Its output
- The gradient coming from the next layer

This allows gradients for all parameters to be computed in time proportional
to the number of parameters in the network.
md
Copy code
## Common Problems in Backpropagation

### Vanishing Gradients

In deep networks, gradients can become extremely small as they propagate
backward through many layers.

As a result:
- Early layers learn very slowly
- Training becomes ineffective

This problem motivated the use of activation functions like ReLU.
md
Copy code
### Exploding Gradients

In some cases, gradients can grow very large during backpropagation.

This leads to:
- Unstable training
- Large, erratic weight updates

Techniques such as proper initialization and normalization help mitigate this issue.
md
Copy code
## Key Takeaways

- Backpropagation computes exact gradients using the chain rule
- It enables efficient training of deep neural networks
- Gradient-related issues influence architecture and activation choices
- Understanding backpropagation is fundamental to understanding deep learning