# Scikit-Learn Guide (Part 2)

# Table of Contents

1. Introduction
2. Supervised vs Unsupervised Learning
3. Regression
4. Linear Regression
5. Logistic Regression
6. Decision Tree
7. Random Forest
8. K-Nearest Neighbors (KNN)
9. Support Vector Machine (SVM)
10. Naive Bayes
11. Clustering
12. K-Means Clustering
13. DBSCAN
14. Dimensionality Reduction (PCA)
15. Choosing the Right Algorithm
16. Summary

---

# 1. Introduction

After preprocessing the data, the next step is selecting a Machine Learning algorithm.

Different algorithms are designed for different types of problems. Choosing the correct algorithm depends on the type of data and the objective of the project.

---

# 2. Supervised vs Unsupervised Learning

Machine Learning algorithms are generally divided into two main categories.

## Supervised Learning

The model learns from labeled data, meaning the correct output is already known.

Examples:

- House Price Prediction
- Disease Prediction
- Spam Detection
- Obesity Prediction

Common algorithms:

- Linear Regression
- Logistic Regression
- Decision Tree
- Random Forest
- KNN
- SVM
- Naive Bayes

---

## Unsupervised Learning

The model learns patterns without knowing the correct answers.

Examples:

- Customer Segmentation
- Product Clustering
- Market Analysis
- Recommendation Systems

Common algorithms:

- K-Means
- DBSCAN
- PCA

---

# 3. Regression

Regression algorithms predict continuous numerical values.

Examples:

- House price
- Salary
- Calories burned
- Laptop price
- Temperature

Example:

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

---

# 4. Linear Regression

## What is Linear Regression?

Linear Regression models the relationship between input features and a continuous target using a straight line.

Simple equation:

```
y = mx + b
```

Where:

- y = predicted value
- x = input feature
- m = slope
- b = intercept

---

### Advantages

- Easy to understand.
- Fast training.
- Good baseline model.
- Highly interpretable.

---

### Disadvantages

- Assumes a linear relationship.
- Sensitive to outliers.
- Cannot model complex patterns.

---

### Common Applications

- House prices
- Salary prediction
- Calories burned
- Laptop price prediction

---

# 5. Logistic Regression

Despite its name, Logistic Regression is used for **classification**, not regression.

It predicts the probability that a sample belongs to a class.

Examples:

- Spam or Not Spam
- Fraud Detection
- Disease Prediction
- Pass or Fail

Example:

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

model.fit(X_train, y_train)
```

---

### Advantages

- Simple.
- Fast.
- Easy to interpret.
- Works well for binary classification.

---

### Disadvantages

- Assumes a linear decision boundary.
- Less effective for complex datasets.

---

# 6. Decision Tree

Decision Trees split data into smaller groups based on feature values.

Example:

```
Age > 30?

      Yes
       |
Income > 5000?
```

Example code:

```python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier()

model.fit(X_train, y_train)
```

---

### Advantages

- Easy to visualize.
- Handles numerical and categorical data.
- No feature scaling required.

---

### Disadvantages

- Can overfit.
- Sensitive to small changes in data.

---

### Applications

- Medical diagnosis
- Customer segmentation
- Credit approval

---

# 7. Random Forest

Random Forest combines many Decision Trees.

Instead of relying on one tree, it averages the predictions from multiple trees.

Example:

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()

model.fit(X_train, y_train)
```

---

### Advantages

- High accuracy.
- Reduces overfitting.
- Handles missing patterns better.
- Works well on many datasets.

---

### Disadvantages

- Slower than a single tree.
- Harder to interpret.

---

### Applications

- Medical diagnosis
- Fraud detection
- Product recommendation
- Customer churn prediction

---

# 8. K-Nearest Neighbors (KNN)

KNN classifies a new sample using the labels of its nearest neighbors.

Example:

```python
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=5)

model.fit(X_train, y_train)
```

---

### Advantages

- Easy to understand.
- No training phase.
- Works well on small datasets.

---

### Disadvantages

- Slow for large datasets.
- Sensitive to feature scaling.
- Sensitive to irrelevant features.

---

### Applications

- Recommendation systems
- Image recognition
- Pattern recognition

---

# 9. Support Vector Machine (SVM)

SVM finds the best boundary that separates different classes.

Example:

```python
from sklearn.svm import SVC

model = SVC()

model.fit(X_train, y_train)
```

---

### Advantages

- High accuracy.
- Effective in high-dimensional spaces.
- Works well with small datasets.

---

### Disadvantages

- Slow on very large datasets.
- Requires feature scaling.
- More difficult to interpret.

---

### Applications

- Face recognition
- Text classification
- Medical diagnosis

---

# 10. Naive Bayes

Naive Bayes is based on Bayes' Theorem.

It assumes that features are independent of each other.

Example:

```python
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()

model.fit(X_train, y_train)
```

---

### Advantages

- Very fast.
- Performs well with text data.
- Works with small datasets.

---

### Disadvantages

- Assumes feature independence.
- May perform poorly when features are strongly correlated.

---

### Applications

- Spam filtering
- Sentiment analysis
- Document classification

---

# 11. Clustering

Clustering groups similar observations together without labels.

Applications:

- Customer segmentation
- Image grouping
- Market analysis
- Recommendation systems

---

# 12. K-Means Clustering

K-Means divides observations into K groups.

Example:

```python
from sklearn.cluster import KMeans

model = KMeans(n_clusters=3)

model.fit(X)
```

---

### Advantages

- Fast.
- Easy to implement.
- Efficient on large datasets.

---

### Disadvantages

- Must choose K beforehand.
- Sensitive to outliers.
- Works best with spherical clusters.

---

### Applications

- Customer segmentation
- Product grouping
- Image compression

---

# 13. DBSCAN

DBSCAN clusters data based on density.

Unlike K-Means, it automatically identifies outliers.

Example:

```python
from sklearn.cluster import DBSCAN

model = DBSCAN()

model.fit(X)
```

---

### Advantages

- Detects outliers.
- Does not require specifying the number of clusters.
- Can find clusters with irregular shapes.

---

### Disadvantages

- Parameter tuning can be difficult.
- Performance decreases with varying densities.

---

### Applications

- Geographic analysis
- Anomaly detection
- Image processing

---

# 14. Principal Component Analysis (PCA)

PCA reduces the number of features while preserving most of the important information.

Example:

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)

X_new = pca.fit_transform(X)
```

---

### Why Use PCA?

- Faster model training.
- Reduce memory usage.
- Remove redundant features.
- Improve visualization.

---

### Advantages

- Reduces dimensionality.
- Removes redundancy.
- Improves computational efficiency.

---

### Disadvantages

- Reduced interpretability.
- Possible loss of information.

---

### Applications

- Data visualization
- Image compression
- Feature reduction

---

# 15. Choosing the Right Algorithm

| Problem | Recommended Algorithm |
|----------|----------------------|
| Predict house prices | Linear Regression |
| Predict calories burned | Linear Regression, Random Forest |
| Predict obesity class | Random Forest, Decision Tree |
| Spam detection | Naive Bayes |
| Customer segmentation | K-Means |
| Fraud detection | Random Forest |
| Medical diagnosis | Random Forest, SVM |
| Recommendation system | KNN |
| Reduce features | PCA |

---

# 16. Summary

Scikit-Learn offers a wide range of machine learning algorithms for both supervised and unsupervised learning.

Choosing the right algorithm depends on the problem, the dataset, and the desired balance between accuracy, interpretability, and computational cost.

In this part, you learned the purpose, advantages, disadvantages, and common applications of the most widely used algorithms in Scikit-Learn. In the next part, we will learn how to evaluate models, compare their performance, perform cross-validation, and tune hyperparameters to build more reliable machine learning systems.