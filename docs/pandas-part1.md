# Pandas Guide

## Table of Contents

1. Introduction
2. What is Pandas?
3. Why Do We Use Pandas?
4. Installation
5. Importing Pandas
6. Core Data Structures

   * Series
   * DataFrame
7. Creating a Series
8. Creating a DataFrame
9. Reading Data
10. Writing Data
11. Inspecting Data
12. Selecting Data
13. Filtering Data
14. Sorting Data
15. Descriptive Statistics
16. Summary

---

# 1. Introduction

Pandas is one of the most important Python libraries for Data Science, Data Analysis, and Machine Learning.

While NumPy is designed for numerical computation, Pandas is designed for working with structured and tabular data such as CSV files, Excel spreadsheets, SQL databases, and JSON files.

Almost every Machine Learning project begins with loading and exploring data using Pandas.

---

# 2. What is Pandas?

Pandas is an open-source Python library built on top of NumPy.

It introduces two powerful data structures:

* Series
* DataFrame

These structures make it easy to organize, clean, manipulate, analyze, and visualize data.

Pandas provides an intuitive interface for working with datasets of any size.

---

# 3. Why Do We Use Pandas?

Real-world datasets are rarely clean.

Before training a Machine Learning model, data usually contains:

* Missing values
* Duplicate records
* Incorrect data types
* Unnecessary columns
* Outliers
* Inconsistent formatting

Pandas provides efficient tools to solve these problems.

It is commonly used for:

* Reading datasets
* Cleaning data
* Data transformation
* Feature engineering
* Exploratory Data Analysis (EDA)
* Preparing datasets for Machine Learning

---

# 4. Installation

Install Pandas using pip:

```bash
pip install pandas
```

Verify the installation:

```bash
pip show pandas
```

Display the installed version:

```python
import pandas as pd

print(pd.__version__)
```

---

# 5. Importing Pandas

The standard convention is:

```python
import pandas as pd
```

The alias `pd` is widely used in tutorials, books, and professional projects.

---

# 6. Core Data Structures

Pandas provides two main data structures.

## Series

A Series is a one-dimensional labeled array.

It is similar to a single column in a spreadsheet.

Example:

```python
import pandas as pd

ages = pd.Series([18, 21, 25, 30])

print(ages)
```

Output:

```
0    18
1    21
2    25
3    30
dtype: int64
```

A Series contains:

* Values
* Index

You can also define custom indexes.

Example:

```python
ages = pd.Series(
    [18,21,25],
    index=["Alice","Bob","John"]
)
```

---

## DataFrame

A DataFrame is the most important object in Pandas.

It is a two-dimensional table composed of rows and columns.

Think of it as an Excel spreadsheet inside Python.

Example:

```python
data = {
    "Name":["Alice","Bob","John"],
    "Age":[20,25,30],
    "City":["Paris","London","Tokyo"]
}

df = pd.DataFrame(data)

print(df)
```

Output:

```
    Name  Age    City
0  Alice   20   Paris
1    Bob   25  London
2   John   30   Tokyo
```

A DataFrame can contain multiple data types:

* Integer
* Float
* String
* Boolean
* DateTime

This flexibility makes it ideal for real-world datasets.

---

# 7. Creating a Series

From a list

```python
numbers = pd.Series([10,20,30])
```

From a dictionary

```python
population = pd.Series({
    "France":68,
    "Japan":124,
    "Canada":39
})
```

Series support mathematical operations:

```python
numbers * 2
```

---

# 8. Creating a DataFrame

From a dictionary

```python
data = {
    "Product":["Laptop","Mouse","Keyboard"],
    "Price":[1200,30,70]
}

df = pd.DataFrame(data)
```

From a list

```python
students = [
    ["Alice",20],
    ["Bob",21],
    ["John",22]
]

df = pd.DataFrame(
    students,
    columns=["Name","Age"]
)
```

From a NumPy array

```python
import numpy as np

arr = np.random.rand(4,3)

df = pd.DataFrame(arr)
```

---

# 9. Reading Data

One of Pandas' strongest features is reading different file formats.

## CSV

```python
df = pd.read_csv("data.csv")
```

This is the most commonly used function in Data Science.

---

## Excel

```python
df = pd.read_excel("sales.xlsx")
```

Useful for business reports.

---

## JSON

```python
df = pd.read_json("data.json")
```

Often used when working with APIs.

---

## SQL Database

```python
df = pd.read_sql(query, connection)
```

Useful when data is stored inside relational databases.

---

## Clipboard

```python
df = pd.read_clipboard()
```

Allows you to quickly import copied tables.

---

# 10. Writing Data

Save to CSV

```python
df.to_csv("output.csv", index=False)
```

Save to Excel

```python
df.to_excel("output.xlsx", index=False)
```

Save to JSON

```python
df.to_json("output.json")
```

Exporting data is useful after cleaning or feature engineering.

---

# 11. Inspecting Data

Display the first rows

```python
df.head()
```

Display the last rows

```python
df.tail()
```

Display dimensions

```python
df.shape
```

Display column names

```python
df.columns
```

Display data types

```python
df.dtypes
```

General information

```python
df.info()
```

Statistical summary

```python
df.describe()
```

These functions should always be used before starting any analysis.

---

# 12. Selecting Data

Select one column

```python
df["Age"]
```

Select multiple columns

```python
df[["Age","Salary"]]
```

Select rows by label

```python
df.loc[0]
```

Select rows by position

```python
df.iloc[0]
```

Select a subset

```python
df.loc[0:5,["Age","Salary"]]
```

Understanding `.loc` and `.iloc` is essential when working with datasets.

---

# 13. Filtering Data

Filter rows

```python
df[df["Age"] > 25]
```

Multiple conditions

```python
df[
    (df["Age"] > 25) &
    (df["Salary"] > 5000)
]
```

Using OR

```python
df[
    (df["Age"] > 25) |
    (df["City"]=="Paris")
]
```

Filtering is one of the most common operations in Data Science.

---

# 14. Sorting Data

Ascending

```python
df.sort_values("Age")
```

Descending

```python
df.sort_values(
    "Salary",
    ascending=False
)
```

Sort multiple columns

```python
df.sort_values(
    ["City","Salary"]
)
```

Sorting helps identify trends and organize datasets.

---

# 15. Descriptive Statistics

Mean

```python
df["Salary"].mean()
```

Median

```python
df["Salary"].median()
```

Maximum

```python
df["Salary"].max()
```

Minimum

```python
df["Salary"].min()
```

Standard deviation

```python
df["Salary"].std()
```

Variance

```python
df["Salary"].var()
```

Count

```python
df["Salary"].count()
```

Unique values

```python
df["City"].unique()
```

Number of unique values

```python
df["City"].nunique()
```

These functions provide a quick overview of your dataset before visualization or model training.

---

# 16. Summary

Pandas is the most widely used library for working with structured data in Python.

It simplifies the process of loading, cleaning, transforming, analyzing, and exporting datasets. Mastering Pandas is an essential step before learning advanced Machine Learning techniques with Scikit-learn or Deep Learning frameworks.

The next part of this guide will cover:

* Handling Missing Values
* Duplicate Data
* Data Cleaning
* GroupBy
* Merge, Join, and Concat
* DateTime Operations
* Feature Engineering
* Advantages
* Disadvantages
* Best Practices
* Common Beginner Mistakes
