# Gradient Descent in Logistic Regression (Using `w` as Coefficient)

Logistic regression models the probability that a given input belongs to a particular class using a sigmoid function. To optimize the model parameters, we use gradient descent, which minimizes a cost function—specifically, the log loss (cross-entropy loss).

## Log Loss Function

The log loss function measures the performance of a classification model that outputs a probability between 0 and 1. For logistic regression, the loss function is:

$$
\mathcal{L}(w) = -\frac{1}{m} \sum_{i=1}^{m} \left[ y^{(i)} \log(\hat{y}^{(i)}) + (1 - y^{(i)}) \log(1 - \hat{y}^{(i)}) \right]
$$

where:
- `w`: The model parameters (coefficients).
- `m`: The number of training examples.
- `x^{(i)}`: The `i`-th training example.
- `y^{(i)}`: The true label for `x^{(i)}`.
- $\hat{y}^{(i)}$: The predicted probability for `x^{(i)}`, defined by the sigmoid function $\sigma(z)$.

The sigmoid function is given by:

$$
\hat{y} = \sigma(z) = \frac{1}{1 + e^{-z}}
$$

with $z = w^T x$.

## Converting Log Loss into Matrix Form

Let `X` be the feature matrix (shape `m × n`), where `m` is the number of training examples and `n` is the number of features. Let `w` be the parameter vector (shape `n × 1`), and `y` be the vector of true labels (shape `m × 1`). Then:

$$
z = X w \quad \text{(shape: } m \times 1\text{)}
$$
$$
\hat{y} = \sigma(X w) \quad \text{(shape: } m \times 1\text{)}
$$

The matrix form of the log loss function is:

$$
\mathcal{L}(w) = -\frac{1}{m} \left[ y^T \log(\hat{y}) + (1 - y)^T \log(1 - \hat{y}) \right]
$$

## Deriving the Gradient of the Log Loss

To apply gradient descent, we need to compute the gradient of the loss function with respect to `w`:

$$
\frac{\partial \mathcal{L}(w)}{\partial w} = -\frac{1}{m} \left[ \frac{\partial}{\partial w} \left( y^T \log(\hat{y}) + (1 - y)^T \log(1 - \hat{y}) \right) \right]
$$

### Gradient of $\log(\hat{y})$

Using $\hat{y} = \sigma(X w)$, the derivative of $\log(\hat{y})$ with respect to `w` is:

$$
\frac{\partial \log(\hat{y})}{\partial w} = X^T (\hat{y} - y)
$$

### Gradient of $\log(1 - \hat{y})$

The derivative of $\log(1 - \hat{y})$ with respect to `w` is:

$$
\frac{\partial \log(1 - \hat{y})}{\partial w} = -X^T (\hat{y} - y)
$$

Combining these parts results in:

$$
\frac{\partial \mathcal{L}(w)}{\partial w} = \frac{1}{m} X^T (\hat{y} - y)
$$

## Gradient Descent Update Rule

Using the gradient computed above, the gradient descent update rule is:

$$
w := w - \alpha \nabla_{w} \mathcal{L}(w)
$$

where $\alpha$ is the learning rate, and $\nabla_{w} \mathcal{L}(w)$ is the gradient:

$$
w := w - \alpha \cdot \frac{1}{m} X^T (\hat{y} - y)
$$

This formula updates the parameters `w` iteratively to minimize the log loss, improving the logistic regression model's ability to predict probabilities for given inputs.
