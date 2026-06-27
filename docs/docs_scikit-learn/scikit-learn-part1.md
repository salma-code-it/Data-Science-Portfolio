# Scikit-Learn Guide (Part 1)

# Table of Contents

1. Introduction
2. What is Scikit-Learn?
3. Why Do We Use Scikit-Learn?
4. Installation
5. Importing Scikit-Learn
6. The Scikit-Learn Workflow
7. The Estimator API
8. Loading Datasets
9. Splitting the Dataset
10. Data Preprocessing
11. Handling Missing Values
12. Encoding Categorical Variables
13. Feature Scaling
14. Pipelines
15. Summary

---

# 1. Introduction

Scikit-Learn is one of the most widely used Machine Learning libraries in Python.

It provides simple and efficient tools for building, training, evaluating, and improving machine learning models.

Unlike TensorFlow or PyTorch, which focus mainly on deep learning, Scikit-Learn specializes in traditional Machine Learning algorithms.

It is suitable for beginners because it offers a consistent and easy-to-learn interface while still being powerful enough for many real-world applications.

---

# 2. What is Scikit-Learn?

Scikit-Learn is an open-source Machine Learning library built on top of:

* NumPy
* SciPy
* Pandas
* Matplotlib

It contains implementations of many machine learning algorithms and preprocessing tools.

Examples include:

* Linear Regression
* Logistic Regression
* Decision Trees
* Random Forest
* Support Vector Machines (SVM)
* K-Nearest Neighbors (KNN)
* Naive Bayes
* K-Means Clustering
* Principal Component Analysis (PCA)

Scikit-Learn also provides tools for:

* Data preprocessing
* Model evaluation
* Feature selection
* Hyperparameter tuning
* Cross-validation
* Pipelines

---

# 3. Why Do We Use Scikit-Learn?

Machine Learning is more than choosing an algorithm.

Before training a model, we often need to:

* Clean the data.
* Handle missing values.
* Encode categorical features.
* Scale numerical features.
* Split the dataset.
* Evaluate model performance.
* Compare different algorithms.

Scikit-Learn provides a complete ecosystem that supports each of these tasks with a consistent API.

---

# 4. Installation

Install Scikit-Learn using pip:

```bash
pip install scikit-learn
```

Check the installation:

```bash
pip show scikit-learn
```

Display the installed version:

```python
import sklearn

print(sklearn.__version__)
```

---

# 5. Importing Scikit-Learn

Unlike NumPy or Pandas, Scikit-Learn is organized into many modules.

Examples:

```python
from sklearn.model_selection import train_test_split
```

```python
from sklearn.preprocessing import StandardScaler
```

```python
from sklearn.linear_model import LinearRegression
```

```python
from sklearn.metrics import accuracy_score
```

Instead of importing the entire library, import only the classes or functions you need.

---

# 6. The Scikit-Learn Workflow

Most machine learning projects follow the same sequence of steps.

```
Collect Data
      ↓
Load Dataset
      ↓
Explore Data
      ↓
Clean Data
      ↓
Preprocess Features
      ↓
Split Train/Test
      ↓
Choose Algorithm
      ↓
Train Model
      ↓
Predict
      ↓
Evaluate
      ↓
Improve Model
      ↓
Save Model
```

This workflow helps ensure that the model is trained and evaluated correctly.

---

# 7. The Estimator API

One of Scikit-Learn's greatest strengths is its consistent interface.

Nearly every estimator follows the same pattern:

1. Create the model.
2. Train the model.
3. Make predictions.
4. Evaluate the model.

Example:

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

predictions = model.predict(X_test)
```

Common methods:

| Method            | Purpose                                                       |
| ----------------- | ------------------------------------------------------------- |
| `fit()`           | Learn from the training data.                                 |
| `predict()`       | Predict outputs for new data.                                 |
| `transform()`     | Transform input data.                                         |
| `fit_transform()` | Fit and transform in one step.                                |
| `score()`         | Return a default evaluation score (depends on the estimator). |

Learning this API means you can work with almost every algorithm in Scikit-Learn using the same approach.

---

# 8. Loading Datasets

Scikit-Learn includes several built-in datasets for learning and experimentation.

Load the Iris dataset:

```python
from sklearn.datasets import load_iris

iris = load_iris()
```

Load the Breast Cancer dataset:

```python
from sklearn.datasets import load_breast_cancer

data = load_breast_cancer()
```

Load the Diabetes dataset:

```python
from sklearn.datasets import load_diabetes
```

You can also use datasets from CSV files with Pandas:

```python
import pandas as pd

df = pd.read_csv("data.csv")
```

Built-in datasets are useful for learning because they are already cleaned and well-structured.

---

# 9. Splitting the Dataset

A model should not be evaluated on the same data used for training.

The standard approach is to split the dataset into:

* Training set
* Testing set

Example:

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

### Explanation of Parameters

| Parameter         | Description                          |
| ----------------- | ------------------------------------ |
| `X`               | Input features.                      |
| `y`               | Target variable.                     |
| `test_size=0.2`   | Reserve 20% of the data for testing. |
| `random_state=42` | Ensures reproducible splits.         |

Using a separate test set provides a more reliable estimate of model performance.

---

# 10. Data Preprocessing

Real-world data often requires preprocessing before model training.

Typical preprocessing tasks include:

* Handling missing values
* Encoding categorical variables
* Scaling numerical features
* Feature engineering
* Removing unnecessary columns

Good preprocessing often has a greater impact on model performance than changing the algorithm.

---

# 11. Handling Missing Values

Many machine learning algorithms cannot work with missing values.

Scikit-Learn provides the `SimpleImputer`.

Import:

```python
from sklearn.impute import SimpleImputer
```

Replace missing values with the mean:

```python
imputer = SimpleImputer(strategy="mean")

X = imputer.fit_transform(X)
```

Available strategies:

| Strategy          | Description                           |
| ----------------- | ------------------------------------- |
| `"mean"`          | Replace with the column mean.         |
| `"median"`        | Replace with the column median.       |
| `"most_frequent"` | Replace with the most common value.   |
| `"constant"`      | Replace with a user-defined constant. |

Choose the strategy based on the type of data and the problem you are solving.

---

# 12. Encoding Categorical Variables

Machine learning models require numerical input.

Categorical variables must therefore be encoded.

### Label Encoding

Useful for ordinal categories.

```python
from sklearn.preprocessing import LabelEncoder

encoder = LabelEncoder()

y = encoder.fit_transform(y)
```

Example:

```
Low → 0

Medium → 1

High → 2
```

---

### One-Hot Encoding

Useful for nominal categories.

```python
from sklearn.preprocessing import OneHotEncoder

encoder = OneHotEncoder()

X = encoder.fit_transform(X)
```

Example:

| Color |
| ----- |
| Red   |
| Blue  |
| Green |

becomes

| Red | Blue | Green |
| --- | ---- | ----- |
| 1   | 0    | 0     |
| 0   | 1    | 0     |
| 0   | 0    | 1     |

One-Hot Encoding prevents the model from assuming an incorrect order between categories.

---

# 13. Feature Scaling

Many algorithms perform better when numerical features are on a similar scale.

Example:

| Feature | Values         |
| ------- | -------------- |
| Age     | 18–60          |
| Salary  | 20,000–100,000 |

Without scaling, the salary feature may dominate because of its larger numerical range.

---

### StandardScaler

Centers the data around zero with a standard deviation of one.

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

X_train = scaler.fit_transform(X_train)

X_test = scaler.transform(X_test)
```

---

### MinMaxScaler

Scales values into a specified range, usually between 0 and 1.

```python
from sklearn.preprocessing import MinMaxScaler

scaler = MinMaxScaler()

X_train = scaler.fit_transform(X_train)

X_test = scaler.transform(X_test)
```

---

### When Should You Scale?

| Algorithm           | Scaling Recommended? |
| ------------------- | -------------------- |
| Linear Regression   | Yes                  |
| Logistic Regression | Yes                  |
| SVM                 | Yes                  |
| KNN                 | Yes                  |
| Neural Networks     | Yes                  |
| Decision Tree       | No                   |
| Random Forest       | No                   |
| XGBoost             | No                   |

---

# 14. Pipelines

Machine learning projects often involve multiple preprocessing steps.

Instead of applying each step manually, Scikit-Learn provides `Pipeline`.

Example:

```python
from sklearn.pipeline import Pipeline
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LogisticRegression

pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", LogisticRegression())
])

pipeline.fit(X_train, y_train)

predictions = pipeline.predict(X_test)
```

### Advantages of Pipelines

* Prevents data leakage.
* Makes code easier to read.
* Simplifies model deployment.
* Ensures preprocessing is always applied consistently.
* Easy to combine with cross-validation and hyperparameter tuning.

Using pipelines is considered a best practice in professional machine learning projects.

---

# 15. Summary

Scikit-Learn provides a consistent and powerful framework for traditional machine learning.

In this first part, you learned:

* What Scikit-Learn is
* How to install and import it
* The standard machine learning workflow
* The Estimator API
* How to split datasets
* How to preprocess data
* How to handle missing values
* How to encode categorical variables
* How to scale numerical features
* How to build preprocessing pipelines

These concepts form the foundation of nearly every machine learning project. In the next part, we will explore the most commonly used machine learning algorithms for regression, classification, clustering, and dimensionality reduction.
