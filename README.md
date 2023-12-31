# Machine-Learning
Summary of my journey of learning machine learning
# Day 1
Machine learning is a fascinating field that involves developing algorithms and models capable of learning patterns and making predictions or decisions based on data. It enables computers to automatically learn and improve from experience without being explicitly programmed.

Supervised learning is one prominent category in machine learning, where the algorithm learns from a labeled dataset. In supervised learning, both input data and corresponding desired output (labels) are provided. The algorithm analyzes the relationship between the inputs and outputs and builds a model that can predict the output for new, unseen inputs.

On the other hand, unsupervised learning takes a different approach. In unsupervised learning, only the input data is available, without any explicit labels or desired outputs. The algorithm's task is to identify patterns, relationships, or structures within the data. It aims to uncover underlying insights, clusters, or associations in an unlabeled dataset, making it a powerful tool for data exploration and understanding.

# Day 2
Regression is a supervised learning technique in machine learning that is used for predicting continuous numerical values based on input features. It is a statistical approach that estimates the relationship between a dependent variable and one or more independent variables.
Linear regression builds a model which establishes a relationship between features and targets
For simple linear regression, the model has two parameters  w and b whose values are 'fit' using training data , once a model's parameters have been determined, the model can be used to make predictions on novel data.

Model representation lab -1
https://github.com/NishchalvPandit/Machine-Learning/blob/main/code/model%20representation%201.ipynb
# Cost function
A cost function, denoted by J, is a mathematical function that quantifies the difference between the target (or original) value and the predicted value in a regression problem. It serves as a measure of how well the model is performing.


![image](https://github.com/NishchalvPandit/Machine-Learning/assets/132006735/ced14a85-931e-4b75-8963-c7299ee409ef)

Cost function lab-2
https://github.com/NishchalvPandit/Machine-Learning/blob/main/code/cost%20function%20lab.ipynb

# Day 3
## Gradient descent

Gradient descent is a technique in machine learning, aimed at iteratively minimizing a given cost function by adjusting model parameters based on calculated gradients. This method dynamically selects the steepest descent path during each iteration, facilitating efficient movement towards local or global minima. Widely applied in tasks like neural network training, linear regression, and logistic regression, gradient descent accelerates convergence and enhances optimization efficiency, despite potential challenges like local minima.

![image](https://github.com/NishchalvPandit/Machine-Learning/assets/132006735/32823b94-96c1-4e0a-b424-ff47553de42d)

## Day 4
## Feature scaling

Feature scaling is a preprocessing step in machine learning that adjusts the range of your input features to make them more suitable for gradient descent optimization and ensure that no single feature dominates the learning process.

Two common techniques for feature scaling are:

## Normalization (Min-Max Scaling):

## X_normalized = (X - X_min) / (X_max - X_min)

## Standardization (Z-score Normalization):

## X_standardized = (X - X_mean) / X_stddev
