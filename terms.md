# Descriptive vs Inferential Statistics
## Descriptive Statistics
Identify import elements in a dataset
## Inferential Statistics
Explain those elements via relationships with other elements

# Dimensionality
## Uni-dimensional 
Data points represented on a single line
Analyzed using statistics such as mean, median, standard deviation 
## Bi-dimensional or Multi-dimensional
Data points represented on a graph
Analyzed using regression

# Best-fit Line
The goal of regression is to find the line that best fits the plotted data.
The distance each point is from a given line is the error.
The best fit line is that where the sum of the squares of the errors is minimum (Minimum Least Square Error).
Residuals of a regression are the difference between actual and fitted values of the dependent variable. Should:
- have zero mean
- common variance
- be independent of each other
- be independent of x
- be normally distributed

Errors and residuals are closely related but different. At a high-level, they can be considered the same.

# $R^2$

A measure of how well the linear regression fits the underlying data.
Between 0% and 100%
Always increases by adding new x variables, can lead to overfitting

# $Adjusted-R^2 (R^2 * penalty)$
Preferred for multiple regression
Increases if irrelevant variables are detected (variables whose F-ratio <1)

# Categorical Variables
Take on discrete values
e.g., true/false, male/female, 0/1/2

## Regression w/ Categorical Variables
> See `Building Regression Models with scikit-learn > (2) Understanding Linear Regression as a Machine Learning Problem > R-squared and Adjusted R-squared`
Simple regression line
$ y = a + bx $

Multiple regression lines
$ y = a_1 + bx $
$ y = a_2 + bx $

Combined regression line using dummy variable
$ y = a_1 + (a_2 - a_1)D + bx $

D = 0 reduces to $ y = a_1 + bx $
D = 1 reduces to $ y = a_2 + bx $

Requires $k-1$ dummy variables, where $k$ is the number of groups in the category. E.g., male/female would have 1 dummy variable as shown above, buy days of the week would have 6.

The risk otherwise is multicollinearity.

scikit handles this.

# e

# Overfitting
Model performs well on train data but poorly on test data

Techniques to combat overfitting:
- Regularization: Add a penalty to overly complex models
- Cross-validation: Distinct training and validation phases
- Dropout: (Neural Networks Only) Intentionally turn off some neurons during training

## Regularization
Add penalty to object function (loss function that minimized least squared error)
Penalty as function of regression coefficients
- higher and more complex the regression coefficients, higher the penalty
- the model will serve to minimize this penalty 
- forces the linear optimizer to keep it simple and not overfit
- reduces variance error (makes the model less sensitive to the training data)
- increases bias (assumptions about the underlying model)
- a model always a tradeoff between variance and bias

### Regularization Models
- Lasso: Penalize large regression coefficients
- Ridge: Penalize large regression coefficients
- Elastic Net: Combines Lasso & Ridge

Ordinary MSE Regression 

$$ \text{MSE} = \frac{1}{n} \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 $$
 
 Lasso
 \[ \text{Lasso Loss} = \frac{1}{2n} \left( \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 + \alpha \sum_{j=1}^{p} |w_j| \right) \]

$ \alpha $ is a hyperparameter

Ridge
\[ \text{Ridge Loss} = \frac{1}{2n} \left( \sum_{i=1}^{n} (y_i - \hat{y}_i)^2 + \alpha \sum_{j=1}^{p} w_j^2 \right) \]

# Hyperparameter
Model configuration properties that define a model and remain constant during the training of the model - they are part of the model.

Part of a model:
- Inputs (training data)
- Parameters (what we try to figure out, e.g. coefficients)
- Hyperparameters (design, e.g., decision tree depth, alpha is a regularized function)

Parameters change during the training process, hyperparamters don't.

## Grid Search
Specify all possible values for each hyperparameter - each cell is a candidate model.

Use GridSearchCV in scikit for cross validation to evaluate each candidate model.

Very computationally expensive.

Does not differentiate between import and trivial hyperparameters.

## Random search
Alternative to grid search

Random search of a hyperparameter space
