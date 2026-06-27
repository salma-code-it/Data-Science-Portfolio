# Pandas Guide (Part 2)

## Table of Contents

17. Missing Values
18. Duplicate Data
19. Data Cleaning
20. Renaming Columns
21. Changing Data Types
22. GroupBy
23. Merge, Join, and Concat
24. Working with Date and Time
25. Feature Engineering
26. Advantages
27. Disadvantages
28. Best Practices
29. Common Beginner Mistakes
30. Real-World Example
31. Summary

---

# 17. Missing Values

## What Are Missing Values?

Missing values are empty or unavailable data points within a dataset.

Example:

| Name  | Age | Salary |
| ----- | --- | ------ |
| Alice | 25  | 5000   |
| Bob   | NaN | 4200   |
| John  | 30  | NaN    |

Missing values can affect statistical analysis and machine learning models.

---

## Detect Missing Values

```python
df.isnull()
```

Returns a DataFrame of Boolean values indicating missing data.

---

Count missing values in each column:

```python
df.isnull().sum()
```

---

Check if any missing value exists:

```python
df.isnull().any()
```

---

## Remove Missing Values

Remove rows containing missing values:

```python
df.dropna()
```

Remove columns containing missing values:

```python
df.dropna(axis=1)
```

---

## Fill Missing Values

Replace missing values with zero:

```python
df.fillna(0)
```

Replace with the column mean:

```python
df["Age"] = df["Age"].fillna(df["Age"].mean())
```

Replace with the median:

```python
df["Age"] = df["Age"].fillna(df["Age"].median())
```

Replace with the most frequent value:

```python
df["City"] = df["City"].fillna(df["City"].mode()[0])
```

---

## Which Method Should You Use?

| Data Type   | Recommended Method            |
| ----------- | ----------------------------- |
| Numerical   | Mean or Median                |
| Categorical | Mode                          |
| Time Series | Forward Fill or Backward Fill |

---

# 18. Duplicate Data

Duplicate records may occur when collecting data from multiple sources.

Detect duplicates:

```python
df.duplicated()
```

Count duplicates:

```python
df.duplicated().sum()
```

Remove duplicates:

```python
df.drop_duplicates()
```

Remove duplicates based on specific columns:

```python
df.drop_duplicates(subset=["Email"])
```

Always verify duplicates before removing them.

---

# 19. Data Cleaning

Data cleaning prepares raw data for analysis.

Typical tasks include:

* Removing duplicates
* Handling missing values
* Fixing incorrect values
* Removing unnecessary columns
* Standardizing text
* Correcting data types

Example:

```python
df["Gender"] = df["Gender"].str.lower()
```

Remove spaces:

```python
df["Name"] = df["Name"].str.strip()
```

Replace values:

```python
df["Gender"] = df["Gender"].replace({
    "male":"Male",
    "female":"Female"
})
```

---

# 20. Renaming Columns

Rename one column:

```python
df.rename(columns={"old_name":"new_name"})
```

Rename multiple columns:

```python
df.rename(columns={
    "Age":"Customer_Age",
    "Salary":"Monthly_Salary"
})
```

Use descriptive column names whenever possible.

---

# 21. Changing Data Types

Display current data types:

```python
df.dtypes
```

Convert to integer:

```python
df["Age"] = df["Age"].astype(int)
```

Convert to float:

```python
df["Price"] = df["Price"].astype(float)
```

Convert to string:

```python
df["ID"] = df["ID"].astype(str)
```

Convert to datetime:

```python
df["Date"] = pd.to_datetime(df["Date"])
```

Correct data types improve performance and reduce errors.

---

# 22. GroupBy

## What is GroupBy?

GroupBy allows you to split data into groups and perform calculations on each group.

This is one of the most powerful features in Pandas.

Example:

```python
df.groupby("Department")["Salary"].mean()
```

Average salary by department.

---

Count observations:

```python
df.groupby("City").size()
```

---

Multiple aggregations:

```python
df.groupby("Department").agg({
    "Salary":["mean","max","min"],
    "Age":"mean"
})
```

---

Group by multiple columns:

```python
df.groupby(
    ["Department","Gender"]
)["Salary"].mean()
```

---

# 23. Merge, Join, and Concat

Real-world data is often stored in multiple tables.

Pandas provides three main methods.

---

## Merge

Similar to SQL JOIN.

```python
pd.merge(df1, df2, on="Customer_ID")
```

Different join types:

* inner
* left
* right
* outer

---

## Join

Join using indexes.

```python
df1.join(df2)
```

---

## Concat

Combine datasets vertically:

```python
pd.concat([df1, df2])
```

Combine horizontally:

```python
pd.concat([df1, df2], axis=1)
```

---

When to use each?

| Method | Purpose                 |
| ------ | ----------------------- |
| merge  | Combine related tables  |
| join   | Combine using index     |
| concat | Stack datasets together |

---

# 24. Working with Date and Time

Convert text to datetime:

```python
df["Date"] = pd.to_datetime(df["Date"])
```

Extract year:

```python
df["Year"] = df["Date"].dt.year
```

Extract month:

```python
df["Month"] = df["Date"].dt.month
```

Extract day:

```python
df["Day"] = df["Date"].dt.day
```

Extract weekday:

```python
df["Weekday"] = df["Date"].dt.day_name()
```

DateTime features are commonly used in forecasting and time-series analysis.

---

# 25. Feature Engineering

## What is Feature Engineering?

Feature Engineering is the process of creating new useful variables from existing data.

Good features often improve machine learning performance more than changing algorithms.

Example:

Age Groups

```python
df["Age_Group"] = pd.cut(
    df["Age"],
    bins=[0,18,40,60,100],
    labels=["Child","Adult","Middle","Senior"]
)
```

Create BMI

```python
df["BMI"] = df["Weight"] / (df["Height"]**2)
```

Price per GB

```python
df["Price_Per_GB"] = df["Price"] / df["Storage"]
```

Examples of useful engineered features:

* BMI
* Price per Unit
* Income per Family Member
* Age Category
* Purchase Frequency

---

# 26. Advantages

Pandas offers many advantages:

* Easy to learn.
* Excellent documentation.
* Supports many file formats.
* Efficient data manipulation.
* Strong integration with NumPy.
* Compatible with Scikit-learn.
* Large community.
* Ideal for exploratory data analysis.

---

# 27. Disadvantages

Although powerful, Pandas has some limitations.

* Can consume large amounts of memory.
* Slower than specialized big-data frameworks.
* Not designed for distributed computing.
* Large datasets may require Dask, Polars, or Spark.

---

# 28. Best Practices

Always inspect your data before cleaning it.

Use meaningful column names.

Keep raw data unchanged.

Create a cleaned dataset instead of modifying the original.

Check data types after loading a dataset.

Handle missing values before training models.

Document every preprocessing step.

Avoid unnecessary loops.

Use vectorized operations whenever possible.

Save cleaned datasets.

---

# 29. Common Beginner Mistakes

Ignoring missing values.

Ignoring duplicated rows.

Using incorrect data types.

Modifying the original dataset accidentally.

Using loops instead of Pandas operations.

Training a model before cleaning the data.

Not checking the output of preprocessing steps.

---

# 30. Real-World Example

Suppose you have a laptop price prediction dataset.

Typical preprocessing steps include:

1. Load dataset.

```python
df = pd.read_csv("laptops.csv")
```

2. Inspect the data.

```python
df.info()
```

3. Remove duplicates.

```python
df.drop_duplicates()
```

4. Handle missing values.

```python
df.fillna(df.mean(numeric_only=True))
```

5. Convert data types.

6. Create new features.

7. Encode categorical variables.

8. Train a machine learning model.

This pipeline is similar to what data scientists use in production environments.

---

# 31. Summary

Pandas is the standard library for data manipulation in Python.

It provides powerful tools for reading, cleaning, transforming, exploring, and preparing data for machine learning.

Learning Pandas thoroughly is one of the most valuable investments for anyone pursuing a career in Data Science, Machine Learning, or Artificial Intelligence.

Mastering concepts such as missing values, grouping, merging, feature engineering, and data cleaning will significantly improve the quality of your machine learning projects.
