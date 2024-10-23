### Introduction to Softmax Regression in Logistic Regression

Softmax regression, also known as multinomial logistic regression, is an extension of binary logistic regression that allows for multi-class classification. Unlike binary logistic regression, which predicts between two outcomes, softmax regression can handle multiple classes simultaneously. It does this by assigning probabilities to each class and selecting the one with the highest probability as the final prediction.

### Formula and Class Assignment

In multi-class classification, we typically label classes as 1, 2, 3, and so on. For instance, if there are three classes, the data points are assigned to these classes. Logistic regression is applied to each class by converting the multi-class problem into a set of binary classification tasks. For each class, a separate logistic regression model is built to predict whether a data point belongs to that class or not.

For example, given three classes:

- Class 1: The model predicts whether the point belongs to Class 1 or not.
- Class 2: The model predicts whether the point belongs to Class 2 or not.
- Class 3: The model predicts whether the point belongs to Class 3 or not.

This process involves calculating coefficients (weights) for each class by minimizing the log-loss function for each binary classification. After fitting the models, the predictions for each class are obtained, and the class with the highest predicted probability is selected as the final prediction.

### Computational Complexity and Softmax Formula

However, when the number of classes increases, this approach becomes computationally expensive. For each class, we would need to compute the coefficients separately, which involves multiple logistic regressions. This would result in a large number of coefficients and time-consuming calculations.

To address this, softmax regression uses a single model that computes probabilities for all classes at once. The softmax function is applied to the raw predictions (logits), normalizing them into probabilities. The formula for softmax is as follows:

$$\[
P(y=j | x) = \frac{e^{w_j^T x}}{\sum_{k=1}^K e^{w_k^T x}}
\]$$

Here, \( w_j \) represents the coefficients for class \( j \), and the denominator is the sum of exponentials across all classes \( K \). This way, rather than calculating binary classifications for each class, the softmax function enables simultaneous prediction, reducing the complexity of the process.

At the end, for a classification problem with three classes, the softmax regression model calculates a total of 9 coefficients (3 for each class), making it much more efficient. The class with the highest probability is chosen as the final prediction.


