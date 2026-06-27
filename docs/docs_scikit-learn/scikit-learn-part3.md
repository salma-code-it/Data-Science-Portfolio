# Scikit-Learn Guide (Part 3)

# Table of Contents

1. Introduction
2. Why Model Evaluation Matters
3. Regression Metrics
4. Mean Absolute Error (MAE)
5. Mean Squared Error (MSE)
6. Root Mean Squared Error (RMSE)
7. R² Score (Coefficient of Determination)
8. Classification Metrics
9. Accuracy
10. Precision
11. Recall
12. F1 Score
13. Confusion Matrix
14. Classification Report
15. ROC Curve and AUC
16. Cross Validation
17. Hyperparameter Tuning
18. GridSearchCV
19. RandomizedSearchCV
20. Summary

---

# 1. Introduction

After training a machine learning model, the next step is to evaluate its performance.

A model may perform well on the training data but fail when predicting new, unseen data. Therefore, evaluation metrics help determine how well the model generalizes.

Different problems require different evaluation metrics.

- Regression → Numerical metrics (MAE, MSE, RMSE, R²)
- Classification → Accuracy, Precision, Recall, F1 Score, ROC-AUC

---

# 2. Why Model Evaluation Matters

A model with high training accuracy is not always a good model.

Evaluation helps us:

- Compare different algorithms.
- Detect overfitting.
- Detect underfitting.
- Measure prediction errors.
- Improve model performance.

Choosing the right evaluation metric is just as important as choosing the right algorithm.

---

# 3. Regression Metrics

Regression models predict continuous numerical values.

Examples:

- House price
- Salary
- Calories burned
- Laptop price

Common regression metrics include:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- R² Score

---

# 4. Mean Absolute Error (MAE)

MAE measures the average absolute difference between predicted values and actual values.

Example:

```python
from sklearn.metrics import mean_absolute_error

mae = mean_absolute_error(y_test, predictions)

print(mae)
```

Interpretation:

- Lower MAE is better.
- A value of 0 means perfect predictions.

Advantages:

- Easy to understand.
- Less sensitive to outliers than MSE.

Disadvantages:

- Does not penalize large errors strongly.

---

# 5. Mean Squared Error (MSE)

MSE squares prediction errors before averaging them.

Example:

```python
from sklearn.metrics import mean_squared_error

mse = mean_squared_error(y_test, predictions)

print(mse)
```

Advantages:

- Penalizes large errors.
- Widely used.

Disadvantages:

- Sensitive to outliers.
- Harder to interpret because values are squared.

---

# 6. Root Mean Squared Error (RMSE)

RMSE is simply the square root of the Mean Squared Error.

Example:

```python
from sklearn.metrics import mean_squared_error
import numpy as np

rmse = np.sqrt(mean_squared_error(y_test, predictions))

print(rmse)
```

Advantages:

- Same unit as the target variable.
- Easier to interpret than MSE.

Disadvantages:

- Still sensitive to outliers.

---

# 7. R² Score (Coefficient of Determination)

R² measures how well the model explains the variation in the target variable.

Example:

```python
from sklearn.metrics import r2_score

score = r2_score(y_test, predictions)

print(score)
```

Interpretation:

| R² Score | Meaning |
|----------|---------|
| 1.0 | Perfect prediction |
| 0.9 | Excellent |
| 0.7 | Good |
| 0.5 | Moderate |
| 0 | No improvement over predicting the mean |
| Negative | Worse than predicting the mean |

Higher values are better.

---

# 8. Classification Metrics

Classification models predict categories instead of numbers.

Examples:

- Spam or Not Spam
- Fraud or Not Fraud
- Obesity Class
- Disease Prediction

Common metrics:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC

---

# 9. Accuracy

Accuracy measures the proportion of correct predictions.

Example:

```python
from sklearn.metrics import accuracy_score

accuracy = accuracy_score(y_test, predictions)

print(accuracy)
```

Formula:

```
Correct Predictions
-------------------
Total Predictions
```

Advantages:

- Easy to understand.

Disadvantages:

- Can be misleading for imbalanced datasets.

---

# 10. Precision

Precision measures how many predicted positive cases are actually positive.

Example:

```python
from sklearn.metrics import precision_score

precision = precision_score(y_test, predictions)
```

Applications:

- Fraud detection
- Spam detection
- Medical diagnosis

High precision means few false positives.

---

# 11. Recall

Recall measures how many actual positive cases were correctly identified.

Example:

```python
from sklearn.metrics import recall_score

recall = recall_score(y_test, predictions)
```

Applications:

- Cancer detection
- Disease diagnosis
- Security systems

High recall means few false negatives.

---

# 12. F1 Score

F1 Score combines Precision and Recall.

Example:

```python
from sklearn.metrics import f1_score

score = f1_score(y_test, predictions)
```

Advantages:

- Good for imbalanced datasets.
- Balances Precision and Recall.

Higher values indicate better performance.

---

# 13. Confusion Matrix

A Confusion Matrix summarizes prediction results.

Example:

```python
from sklearn.metrics import confusion_matrix

matrix = confusion_matrix(y_test, predictions)

print(matrix)
```

For binary classification:

| | Predicted Positive | Predicted Negative |
|---|---|---|
| Actual Positive | True Positive (TP) | False Negative (FN) |
| Actual Negative | False Positive (FP) | True Negative (TN) |

The confusion matrix helps identify where the model makes mistakes.

---

# 14. Classification Report

Scikit-Learn provides a complete summary of classification performance.

Example:

```python
from sklearn.metrics import classification_report

print(classification_report(y_test, predictions))
```

The report includes:

- Precision
- Recall
- F1 Score
- Support (number of samples)

This is often the first report used to evaluate classification models.

---

# 15. ROC Curve and AUC

The ROC Curve shows the trade-off between the True Positive Rate and the False Positive Rate.

AUC (Area Under the Curve) summarizes the ROC Curve with a single value.

Example:

```python
from sklearn.metrics import roc_auc_score

auc = roc_auc_score(y_test, probabilities)

print(auc)
```

Interpretation:

| AUC | Quality |
|-----|---------|
| 1.0 | Perfect |
| 0.9 | Excellent |
| 0.8 | Good |
| 0.7 | Fair |
| 0.5 | Random guessing |

Higher AUC values indicate better classification performance.

---

# 16. Cross Validation

Instead of evaluating the model using only one train-test split, Cross Validation repeats the process using multiple splits.

Example:

```python
from sklearn.model_selection import cross_val_score
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()

scores = cross_val_score(
    model,
    X,
    y,
    cv=5
)

print(scores)
print(scores.mean())
```

Advantages:

- More reliable evaluation.
- Better use of available data.
- Reduces evaluation bias.

---

# 17. Hyperparameter Tuning

Hyperparameters control how a machine learning algorithm behaves.

Examples:

- Number of trees
- Maximum tree depth
- Learning rate
- Number of neighbors

Choosing good hyperparameters often improves model performance.

---

# 18. GridSearchCV

GridSearchCV tests every possible combination of hyperparameters.

Example:

```python
from sklearn.model_selection import GridSearchCV
from sklearn.ensemble import RandomForestClassifier

parameters = {
    "n_estimators": [100, 200],
    "max_depth": [5, 10]
}

grid = GridSearchCV(
    RandomForestClassifier(),
    parameters,
    cv=5
)

grid.fit(X_train, y_train)

print(grid.best_params_)
```

Advantages:

- Finds the best parameter combination.
- Uses Cross Validation automatically.

Disadvantages:

- Can be slow.

---

# 19. RandomizedSearchCV

RandomizedSearchCV tests only a random subset of parameter combinations.

Example:

```python
from sklearn.model_selection import RandomizedSearchCV

random = RandomizedSearchCV(
    RandomForestClassifier(),
    parameters,
    n_iter=10,
    cv=5
)

random.fit(X_train, y_train)
```

Advantages:

- Faster than GridSearchCV.
- Works well for large parameter spaces.

Disadvantages:

- May not find the absolute best combination.

---

# 20. Summary

Model evaluation is a critical step in every machine learning project.

In this guide, you learned:

- Regression evaluation metrics (MAE, MSE, RMSE, R²)
- Classification evaluation metrics (Accuracy, Precision, Recall, F1 Score)
- Confusion Matrix
- Classification Report
- ROC Curve and AUC
- Cross Validation
- Hyperparameter Tuning
- GridSearchCV
- RandomizedSearchCV

Choosing the right evaluation metric and tuning hyperparameters helps build models that generalize well to new data and perform reliably in real-world applications.