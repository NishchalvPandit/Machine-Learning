## All you need to know about Linear regression
Linear regression is a supervised learning technique used to predict the value of a target variable by finding the best-fit line that minimizes the cost function, usually the Mean Squared Error (MSE). There are three main types:

- Simple Linear Regression: Involves two columns (one input and one output), where a single independent variable is used to predict the dependent variable.
- Multiple Linear Regression: Involves multiple input columns, where more than one independent variable is used to predict the dependent variable.
- Polynomial Regression: Used when the relationship between variables is not linear, and a polynomial function is used to fit the data.
### Simple Linear Regression

Simple Linear Regression is used to predict the relationship between a single independent variable ($x$) and a dependent variable ($y$) by fitting a straight line to the data. The line of best fit can be represented as:
 $$y = mx + b$$ 
where:
-  y  is the predicted value,
-  x  is the input feature,
-  m  is the slope of the line, and
-  b  is the y-intercept.

### Ordinary Least Squares (OLS)

Ordinary Least Squares (OLS) is a method used to find the best-fit line by minimizing the sum of squared differences between the actual and predicted values. This is also known as minimizing the "cost function" or Mean Squared Error (MSE). 

### Closed-form Solution (Analytical Method)

In simple linear regression, we can find the best-fit line using closed-form formulas for  $m$  and  $b$  without requiring iterative optimization. These formulas are derived by setting the derivative of the cost function to zero.

The formulas for the slope  m  and intercept  b  are as follows:

$$
m = \frac{\sum (x_i - \bar{x})(y_i - \bar{y})}{\sum (x_i - \bar{x})^2}
$$

$$
b = \bar{y} - m\bar{x}
$$

where:
$x_i$ and $y_i$ are the individual values of $x$ and $y$, respectively.
$\bar{x}$ and $\bar{y}$ are the means of $x$ and $y$, respectively.


**Deriving the Formulas for m and b in Linear Regression**

**1. Define the Cost Function**

We're using the **Mean Squared Error (MSE)** as our cost function:

```
Cost(m, b) = (1/n) * Σ(y_i - ŷ_i)^2
```

Where:
* `n`: Number of data points
* `y_i`: Actual value of the i-th data point
* `ŷ_i`: Predicted value of the i-th data point (mx_i + b)

**2. Substitute `ŷ_i`**

```
Cost(m, b) = (1/n) * Σ(y_i - (mx_i + b))^2
```

**3. Calculate Partial Derivatives**

**a. Partial Derivative with respect to b**
```
∂Cost/∂b = (1/n) * Σ2 * (y_i - (mx_i + b)) * (-1)
```
Simplifying:
```
∂Cost/∂b = (-2/n) * Σ(y_i - mx_i - b)
```

**b. Partial Derivative with respect to m**
```
∂Cost/∂m = (1/n) * Σ2 * (y_i - (mx_i + b)) * (-x_i)
```
Simplifying:
```
∂Cost/∂m = (-2/n) * Σx_i * (y_i - mx_i - b)
```

**4. Set the Derivatives to Zero**

To find the minimum of the cost function, we set the partial derivatives to zero:

**a. For b**
```
(-2/n) * Σ(y_i - mx_i - b) = 0
```
Simplifying:
```
Σy_i - mΣx_i - nb = 0
```
Rearranging:
```
b = (Σy_i - mΣx_i) / n
```

**b. For m**
```
(-2/n) * Σx_i * (y_i - mx_i - b) = 0
```
Simplifying:
```
Σx_i * y_i - mΣx_i^2 - bΣx_i = 0
```
Substituting the expression for b:
```
Σx_i * y_i - mΣx_i^2 - [(Σy_i - mΣx_i) / n] * Σx_i = 0
```
After some algebraic manipulations, we get:

```
m = (n * Σ(x_i * y_i) - Σx_i * Σy_i) / (n * Σx_i^2 - (Σx_i)^2)
```

**Therefore, the formulas for m and b are:**

$$
m = \frac{n \sum(x_i * y_i) - \sum x_i \sum y_i}{n \sum x_i^2 - (\sum x_i)^2}
$$

$$
b = \bar{y} - m\bar{x}
$$




### Non-closed-form Solution (Gradient Descent)

For larger datasets, we often use an iterative optimization method like Gradient Descent, especially when extending to multiple or polynomial regressions. Gradient Descent minimizes the cost function by iteratively adjusting $m$ and $b$ until the error is minimized.
