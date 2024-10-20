
# Logistic regression
Logistic regression is a statistical method used for binary classification problems. It predicts the probability that a given input point belongs to a certain class, typically represented as 0 or 1.
The data must be linearly separable to use logistic regression.

# Perceptron method:

Prediction: The algorithm predicts the class of input points based on a linear decision boundary.
Weight Adjustment: If a point is correctly classified, no changes are made to the coefficients (weights). However, if the point is misclassified, the weights are adjusted to pull the decision boundary closer to the misclassified point.

### Perceptron Algorithm

1. **Input Representation:**  
   To include the intercept (bias) in the model, we augment the input feature vector x by adding a 1:

   x' = [1, x_1, x_2, ..., x_n]

   This allows us to treat the intercept as a weight w_0, resulting in:

   z = w · x' = w_0 · 1 + w_1 · x_1 + w_2 · x_2 + ... + w_n · x_n
   z=∑ (from i=0 to n) of wᵢ xᵢ

   Here, w is the vector of weights, including w_0 for the intercept.

3. **Prediction:**  
   The prediction Ŷ is made using the step function:

   Ŷ = 
   {
       1 if z > 0 
       0 otherwise 
   }

   

5. **Weight Update Rule:**

   **Pulling and Pushing the Decision Boundary:**
   - **Pulling the line (towards a misclassified positive point):**  
     If a point is misclassified as negative (Y = 1, Ŷ = 0), we need to pull the decision boundary towards this point:

     w = w + η x

   - **Pushing the line (away from a misclassified negative point):**  
     If a point is misclassified as positive (Y = 0, Ŷ = 1), we need to push the decision boundary away from this point:

     w = w - η x
  
     Combining these two formulas in one we get the formula below:

   w ← w + η (Y - Ŷ) x'

   where:
   - η is the learning rate (a small positive constant).
   - Y is the actual class label (0 or 1).
   - Ŷ is the predicted class label.

7. **Bias Update:**  
   The intercept (bias) is now effectively updated along with the weights:

   w_0 ← w_0 + η (Y - Ŷ)

### Summary
By augmenting the input feature vector to include a constant value of 1, we allow the perceptron to learn the intercept as part of the weight vector. This results in a more unified approach to calculating the weighted sum z and simplifies the representation of the model.

# Perceptron trick in python

check out [Perceptron algorithm](https://github.com/NishchalvPandit/Machine-Learning/blob/main/logisticregressionusingperceptron.ipynb
)



