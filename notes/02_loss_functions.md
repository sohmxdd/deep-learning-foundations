# Loss Functions

Loss functions define the objective a machine learning or deep learning model
optimizes during training. They quantify the error between predictions and
ground truth values.

Choosing the correct loss function is critical, as it directly affects
learning behavior, convergence speed, and final model performance.

## Why Loss Functions Matter

- They guide gradient-based optimization
- They define what the model considers “good” or “bad” predictions
- An inappropriate loss can prevent learning entirely

## Regression Loss Functions

Regression problems involve predicting continuous numerical values.
The choice of loss function determines how prediction errors are penalized.

### Mean Squared Error (MSE)

Mean Squared Error penalizes the square of the difference between predicted
and actual values.

Key characteristics:
- Larger errors are penalized more heavily
- Smooth and differentiable everywhere
- Sensitive to outliers

MSE is commonly used when large errors are especially undesirable.

### Mean Absolute Error (MAE)

Mean Absolute Error penalizes the absolute difference between predictions
and actual values.

Key characteristics:
- Penalizes errors linearly
- More robust to outliers than MSE
- Not differentiable at zero (handled in practice)

MAE is preferred when robustness to outliers is important.

## Classification Loss Functions

Classification tasks involve predicting discrete class labels.
Loss functions in classification are usually probabilistic.

### Binary Crossentropy

Binary Crossentropy is used for binary classification problems.
It measures how far predicted probabilities are from the true labels.

It works particularly well with:
- Sigmoid activation functions
- Probabilistic outputs between 0 and 1

### Categorical Crossentropy

Categorical Crossentropy is used for multi-class classification problems
where targets are one-hot encoded.

It compares the predicted probability distribution with the true
class distribution.
