# Building Your First scikit-learn Solution

## General Notes

ML Problem/Algorithm Types

- Classification: True/false, yes/no, cat/bird/mouse
- Predict continuous numeric value: Price of house given location and number of rooms
- Clustering: Find logical groupings in data
- Dimensionality Reduction: Extract significant features from data

## Classification

Logistic Regression
Binary Classification
Multi-label

### Classification Algorithms

- Logistic regression
- Naive Bayes
- Support Vector Machines
- Decision Tree
  Classification Model (Classifier)

### Training

Goal of training is to minimize the loss function
Objective function / loss function / cost function

### Logistic Regression

Find how probabilities are changed by actions
The output is a probability score
Trying to find the best fit of an S curve to estimate probabilities p(yi) = 1 / (1 + e^-(A+Bxi))
The outcome predicted by the logistic regression model is the one that has the highest probability score

### Loss Function

Cross entropy intuition
Minimize loss of model to improve the models parameters
Linear regression loss fucntion is mean swqured error (how far is line from data points)
Logisitc regression functionn loss function is cross entropy
Low entropy would mean that the actual and predicated values are in sync (opposite for hgih entropy)

### Accuracy, Precision, Recall

Accuracy is not always a good metric (skewed data, 1 in 100)

Accuracy = (TP + TN) / N Instances
Precision = Accuracy when classifier flags cancer (TP + FP) / N Subset
Recall = Accuracy when cancer is actually present (TP + FN) / N Subset

#### Confusion Matrix

A grid tabulating the predicted labels vs actual labels (will have as many rows/categories as exist ind data)
True positive - Has cancer, Actual = predicted
True negative - No cancer, Actual = predicted  
False positive - No cancer, Actual != predicted
False negative - Has cancer, Actual != predicted
Accuracy = (TP + TN) / N Instances

### Decision Threshold

You decide the P threshold

#### Precision-Recall Tradeoff

0

- Always positive classifier
- E.g., predicts that everyone has cancer
- Recall is 100% (always accurately identifies people with cancer)
- Low precision (always identifies as having cancer even when doesn't)
- Not conservative enough

1

- Always negative classifier
- E.g., predicts that no one has cancer
- Recall = 0% (never accurately predicates people with cancer)
- Precision = Infinite (cancer is never flagged so N = 0)
- Very conservative

#### Heuristics (ROC Curve)

Used to identify P
We want true positive rate to be as high as possible and false positive rate to be as low as possible
ROC Curve (Receiver Operating Characteristic) represents true positive rate vs false positive rate
Plot points for different P values (hyperparameter tuning) - choose the point with max TP and min FP

### Types of Classification

- Binary Classification (two possible values - e.g., true/false)
- Multiclass (n possible values - binary is actually just a special case)
- Multilabel output is tuple of multiple BINARY variables ([true, male], [false, female])
- Multioutput output is multiclass (NON BINARY) and multilabel ([Sunday, January])

#### Algorithms

Inherently Multilabel - Naive Bayes
Binary Classification (can be generalized for multilabel classification)

- Logistic regression
- Support Vector Machines

##### Generalizing Binary Classifiers

Train multiple binary classifiers

One Versus All
(0 - 9 = 10)
One for each digit
Predicted label = output of detector with highest score

One vs One
(0 - 9 = 45)
N(N-1)/2 classifiers
Use combinations, each classifier detects between pair of digits (duel between the two)
Predicated label = output of digit that wins most duels

### Hands On

Python 3.10.9 (3.7.1)
scikit-learn (0.20) - comes with numpy and scipy
Jupyter (4.4.0)
PIP 22.3.1 (18.1)

-

pip install -U scikit-learn
jupyter notebook

# 9/15 Regression
## e
Euler's Number 'e' is a numerical constant used in mathematical calculations. The value of e is 2.718281828459045…so on. Just like pi(π), e is also an irrational number. It is described basically under logarithm concepts. 'e' is a mathematical constant, which is basically the base of the natural logarithm.

## Negative Exponent
Small Numbers

Negative exponents tell us how many times we have to multiply the reciprocal of the base number. For example, 2-2. The equivalent expression of 2-2 is (½)× (½).