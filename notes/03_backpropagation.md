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
