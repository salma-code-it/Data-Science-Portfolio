# Seaborn Guide

# Table of Contents

1. Introduction
2. What is Seaborn?
3. Why Do We Use Seaborn?
4. Seaborn vs Matplotlib
5. Installation
6. Importing Seaborn
7. Built-in Datasets
8. Themes and Styles
9. Figure Size
10. Line Plot
11. Scatter Plot
12. Bar Plot
13. Count Plot
14. Histogram
15. KDE Plot
16. Distribution Plot
17. Summary

---

# 1. Introduction

Seaborn is a high-level Python library for creating attractive and informative statistical graphics.

It is built on top of Matplotlib, which means Seaborn uses Matplotlib internally while providing a simpler and more expressive interface.

In Data Science and Machine Learning, visualization is one of the most important steps during Exploratory Data Analysis (EDA). Seaborn makes it easy to understand patterns, relationships, distributions, and correlations within a dataset.

---

# 2. What is Seaborn?

Seaborn is an open-source visualization library specifically designed for statistical graphics.

Unlike Matplotlib, which focuses on general plotting, Seaborn provides functions that automatically create beautiful and informative visualizations with minimal code.

Seaborn integrates naturally with Pandas DataFrames, allowing you to visualize data directly from tables without manually extracting columns.

---

# 3. Why Do We Use Seaborn?

Before training a Machine Learning model, we need to understand the data.

Seaborn helps us:

- Explore the distribution of variables.
- Identify relationships between features.
- Detect outliers.
- Visualize correlations.
- Compare categories.
- Understand class imbalance.
- Present results clearly.

Instead of writing many customization commands in Matplotlib, Seaborn automatically produces aesthetically pleasing graphs.

---

# 4. Seaborn vs Matplotlib

Although Seaborn is built on top of Matplotlib, the two libraries serve slightly different purposes.

| Matplotlib | Seaborn |
|------------|----------|
| General plotting library | Statistical visualization library |
| Highly customizable | Easier to use |
| Requires more code | Requires less code |
| Better for full customization | Better for Data Science |
| Foundation library | Built on top of Matplotlib |

In practice:

- Use Matplotlib when you need complete control over every element of the figure.
- Use Seaborn when performing data analysis or exploratory data analysis.

Many Data Scientists combine both libraries in the same project.

---

# 5. Installation

Install Seaborn using pip.

```bash
pip install seaborn
```

Check the installation.

```bash
pip show seaborn
```

Display the installed version.

```python
import seaborn as sns

print(sns.__version__)
```

---

# 6. Importing Seaborn

The standard import is

```python
import seaborn as sns
```

Most projects also import Matplotlib.

```python
import matplotlib.pyplot as plt
```

This allows additional customization when needed.

---

# 7. Built-in Datasets

Seaborn includes several datasets for learning and experimentation.

Display available datasets.

```python
sns.get_dataset_names()
```

Load the Titanic dataset.

```python
titanic = sns.load_dataset("titanic")
```

Load the Iris dataset.

```python
iris = sns.load_dataset("iris")
```

Other popular datasets include:

- diamonds
- penguins
- tips
- flights
- mpg
- planets

These datasets are useful for practicing visualization techniques.

---

# 8. Themes and Styles

One advantage of Seaborn is its built-in themes.

Default theme:

```python
sns.set_theme()
```

White background

```python
sns.set_style("white")
```

Dark grid

```python
sns.set_style("darkgrid")
```

White grid

```python
sns.set_style("whitegrid")
```

Dark

```python
sns.set_style("dark")
```

Ticks

```python
sns.set_style("ticks")
```

Themes improve the appearance of visualizations without requiring manual customization.

---

# 9. Figure Size

Since Seaborn uses Matplotlib, figure size is adjusted with Matplotlib.

```python
plt.figure(figsize=(8,5))
```

Example

```python
plt.figure(figsize=(10,6))

sns.scatterplot(data=df, x="Age", y="Salary")

plt.show()
```

---

# 10. Line Plot

Line plots display trends over ordered values such as time.

Example

```python
sns.lineplot(
    data=df,
    x="Month",
    y="Sales"
)

plt.show()
```

Applications

- Stock prices
- Temperature
- Revenue
- Population growth

---

# 11. Scatter Plot

Scatter plots visualize relationships between numerical variables.

Example

```python
sns.scatterplot(
    data=df,
    x="Height",
    y="Weight"
)

plt.show()
```

Color by category

```python
sns.scatterplot(
    data=df,
    x="Height",
    y="Weight",
    hue="Gender"
)
```

Scatter plots help identify

- Correlations
- Clusters
- Outliers

---

# 12. Bar Plot

Bar plots compare averages across categories.

Example

```python
sns.barplot(
    data=df,
    x="Department",
    y="Salary"
)

plt.show()
```

Applications

- Average salary
- Average sales
- Average exam scores

Unlike Matplotlib's bar chart, Seaborn automatically computes summary statistics.

---

# 13. Count Plot

Count plots display the frequency of each category.

Example

```python
sns.countplot(
    data=df,
    x="Gender"
)

plt.show()
```

Applications

- Gender distribution
- Product categories
- Customer segments
- Class balance

This is one of the most commonly used charts during Exploratory Data Analysis.

---

# 14. Histogram

Histograms visualize numerical distributions.

Example

```python
sns.histplot(
    data=df,
    x="Age"
)

plt.show()
```

Histogram with KDE

```python
sns.histplot(
    data=df,
    x="Age",
    kde=True
)

plt.show()
```

Applications

- Age distribution
- Income distribution
- Price distribution

---

# 15. KDE Plot

KDE stands for Kernel Density Estimation.

It estimates the probability density of numerical data.

Example

```python
sns.kdeplot(
    data=df,
    x="Age"
)

plt.show()
```

Filled KDE

```python
sns.kdeplot(
    data=df,
    x="Age",
    fill=True
)

plt.show()
```

KDE plots provide a smooth representation of a distribution.

---

# 16. Distribution Plot

Distribution plots combine histograms and density estimation.

Example

```python
sns.displot(
    data=df,
    x="Salary"
)
```

With KDE

```python
sns.displot(
    data=df,
    x="Salary",
    kde=True
)
```

Applications

- Income distribution
- Product prices
- Student grades

Distribution plots are widely used to determine whether data follows a normal distribution.

---

# 17. Summary

Seaborn simplifies statistical visualization by providing high-level plotting functions built on top of Matplotlib.

Its integration with Pandas DataFrames and automatic styling make it one of the most widely used visualization libraries in Data Science and Machine Learning.

Understanding line plots, scatter plots, count plots, bar plots, histograms, and KDE plots is an essential first step before exploring more advanced visualizations such as heatmaps, pair plots, violin plots, and regression plots.