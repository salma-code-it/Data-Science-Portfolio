# Matplotlib Guide

# Table of Contents

1. Introduction
2. What is Matplotlib?
3. Why Do We Use Matplotlib?
4. Installation
5. Importing Matplotlib
6. Pyplot
7. Figure and Axes
8. Creating Your First Plot
9. Line Plot
10. Scatter Plot
11. Bar Chart
12. Horizontal Bar Chart
13. Histogram
14. Pie Chart
15. Box Plot
16. Subplots
17. Plot Customization
18. Saving Figures
19. Advantages
20. Disadvantages
21. Best Practices
22. Common Beginner Mistakes
23. Summary

---

# 1. Introduction

Matplotlib is one of the most popular Python libraries for data visualization.

It allows you to transform raw numerical data into charts and graphs that are easier to understand and analyze.

Data visualization is an essential part of Data Science because it helps identify patterns, trends, correlations, and anomalies before building Machine Learning models.

Matplotlib is considered the foundation of visualization libraries in Python. Many libraries such as Seaborn are built on top of Matplotlib.

---

# 2. What is Matplotlib?

Matplotlib is an open-source plotting library developed for Python.

It provides a flexible interface for creating static, animated, and interactive visualizations.

It supports many chart types, including:

* Line charts
* Scatter plots
* Bar charts
* Histograms
* Pie charts
* Box plots
* Heatmaps (through additional libraries)
* Subplots
* 3D plots

---

# 3. Why Do We Use Matplotlib?

Machine Learning models require understanding the dataset before training.

Visualization helps us:

* Explore the data
* Detect missing values
* Identify outliers
* Understand relationships between variables
* Compare categories
* Present results clearly

Instead of reading thousands of numbers, graphs allow us to understand data quickly.

---

# 4. Installation

Install Matplotlib using pip.

```bash
pip install matplotlib
```

Check the installation.

```bash
pip show matplotlib
```

Display the installed version.

```python
import matplotlib

print(matplotlib.__version__)
```

---

# 5. Importing Matplotlib

The standard import is:

```python
import matplotlib.pyplot as plt
```

The alias `plt` is the standard convention used in almost every Data Science project.

---

# 6. Pyplot

`pyplot` is a module that provides functions similar to MATLAB plotting commands.

It makes creating charts simple.

Most visualizations begin with:

```python
import matplotlib.pyplot as plt
```

---

# 7. Figure and Axes

Matplotlib creates plots using two main objects.

## Figure

A Figure is the entire window or canvas that contains one or more plots.

## Axes

Axes represent an individual chart inside the figure.

Example:

```python
fig, ax = plt.subplots()
```

Think of it like this:

```
Figure
│
├── Axes
├── Axes
└── Axes
```

---

# 8. Creating Your First Plot

```python
import matplotlib.pyplot as plt

x = [1,2,3,4,5]
y = [2,4,6,8,10]

plt.plot(x, y)

plt.show()
```

This creates a simple line chart.

---

# 9. Line Plot

A line plot is used to display trends over time or ordered values.

Example:

```python
x = [1,2,3,4,5]
sales = [100,150,170,220,280]

plt.plot(x, sales)

plt.show()
```

Common applications:

* Stock prices
* Temperature
* Sales over time
* Population growth

---

# 10. Scatter Plot

A scatter plot displays the relationship between two numerical variables.

Example:

```python
height = [160,165,170,175,180]
weight = [55,60,68,74,82]

plt.scatter(height, weight)

plt.show()
```

Common applications:

* Height vs Weight
* Age vs Salary
* Calories vs Exercise

Scatter plots are useful for detecting correlations and outliers.

---

# 11. Bar Chart

Bar charts compare categories.

Example:

```python
products = ["Laptop","Phone","Tablet"]

sales = [120,90,45]

plt.bar(products, sales)

plt.show()
```

Common applications:

* Product sales
* Student grades
* Company revenue

---

# 12. Horizontal Bar Chart

```python
plt.barh(products, sales)

plt.show()
```

Useful when category names are long.

---

# 13. Histogram

Histograms show how data is distributed.

Example:

```python
import numpy as np

ages = np.random.randint(18,60,100)

plt.hist(ages)

plt.show()
```

Histograms help answer questions like:

* Is the data normally distributed?
* Are there outliers?
* Is the data skewed?

---

# 14. Pie Chart

Pie charts display proportions.

Example:

```python
labels = ["Python","Java","C++"]

students = [60,25,15]

plt.pie(
    students,
    labels=labels,
    autopct="%1.1f%%"
)

plt.show()
```

Pie charts should only be used for a small number of categories.

---

# 15. Box Plot

A box plot summarizes numerical data.

Example:

```python
salary = [2000,2200,2500,2700,3000,5000]

plt.boxplot(salary)

plt.show()
```

A box plot displays:

* Minimum
* First Quartile (Q1)
* Median
* Third Quartile (Q3)
* Maximum
* Outliers

Box plots are widely used for detecting unusual observations.

---

# 16. Subplots

Subplots allow multiple charts inside one figure.

Example:

```python
fig, ax = plt.subplots(1,2)

ax[0].plot([1,2,3],[1,4,9])

ax[1].bar(
    ["A","B","C"],
    [5,3,8]
)

plt.show()
```

Useful when comparing multiple visualizations.

---

# 17. Plot Customization

## Title

```python
plt.title("Monthly Sales")
```

---

## X-axis Label

```python
plt.xlabel("Month")
```

---

## Y-axis Label

```python
plt.ylabel("Sales")
```

---

## Grid

```python
plt.grid(True)
```

---

## Legend

```python
plt.plot(x,y,label="Sales")

plt.legend()
```

---

## Change Figure Size

```python
plt.figure(figsize=(8,5))
```

---

## Change Line Style

```python
plt.plot(
    x,
    y,
    linestyle="--"
)
```

---

## Change Marker

```python
plt.plot(
    x,
    y,
    marker="o"
)
```

---

# 18. Saving Figures

Instead of displaying a figure, save it.

```python
plt.savefig("figure.png")
```

High-quality PDF:

```python
plt.savefig(
    "figure.pdf",
    dpi=300
)
```

Saving figures is useful for reports and presentations.

---

# 19. Advantages

* Easy to learn.
* Large community.
* Highly customizable.
* Excellent documentation.
* Works well with NumPy.
* Works well with Pandas.
* Suitable for scientific visualization.
* Used in research and industry.

---

# 20. Disadvantages

* Syntax can become verbose.
* Some charts require many customization commands.
* Statistical visualization is easier with Seaborn.
* Interactive visualizations are limited compared to Plotly.

---

# 21. Best Practices

Always label your axes.

Always give your chart a title.

Use readable figure sizes.

Avoid unnecessary colors.

Keep charts simple.

Choose the correct chart type.

Save high-resolution figures for reports.

Use legends only when needed.

---

# 22. Common Beginner Mistakes

Using the wrong chart type.

Forgetting `plt.show()`.

Creating unreadable labels.

Using too many colors.

Displaying too much information in one graph.

Ignoring chart titles.

Not labeling axes.

---

# 23. Summary

Matplotlib is the foundation of data visualization in Python.

It enables data scientists to transform raw data into meaningful visualizations that support exploration, communication, and decision-making.

Understanding line plots, scatter plots, bar charts, histograms, box plots, and figure customization is essential before learning advanced visualization libraries such as Seaborn.

---

# Frequently Used Functions

The table below summarizes the Matplotlib functions that every Data Scientist should know.

| Function | Description | Example |
|----------|-------------|---------|
| `plt.plot()` | Creates a line chart. | `plt.plot(x, y)` |
| `plt.scatter()` | Creates a scatter plot to show the relationship between two numerical variables. | `plt.scatter(x, y)` |
| `plt.bar()` | Creates a vertical bar chart. | `plt.bar(categories, values)` |
| `plt.barh()` | Creates a horizontal bar chart. | `plt.barh(categories, values)` |
| `plt.hist()` | Creates a histogram to visualize data distribution. | `plt.hist(data)` |
| `plt.boxplot()` | Displays a box plot to detect outliers and summarize data. | `plt.boxplot(data)` |
| `plt.pie()` | Creates a pie chart to show proportions. | `plt.pie(values)` |
| `plt.title()` | Adds a title to the chart. | `plt.title("Sales Report")` |
| `plt.xlabel()` | Sets the label of the x-axis. | `plt.xlabel("Month")` |
| `plt.ylabel()` | Sets the label of the y-axis. | `plt.ylabel("Sales")` |
| `plt.legend()` | Displays the legend. | `plt.legend()` |
| `plt.grid()` | Shows grid lines on the chart. | `plt.grid(True)` |
| `plt.figure()` | Creates a new figure and allows you to define its size. | `plt.figure(figsize=(8,5))` |
| `plt.subplots()` | Creates one or more subplots inside the same figure. | `fig, ax = plt.subplots()` |
| `plt.xlim()` | Sets the range of the x-axis. | `plt.xlim(0, 100)` |
| `plt.ylim()` | Sets the range of the y-axis. | `plt.ylim(0, 500)` |
| `plt.xticks()` | Customizes x-axis tick positions or labels. | `plt.xticks(rotation=45)` |
| `plt.yticks()` | Customizes y-axis tick positions or labels. | `plt.yticks(fontsize=10)` |
| `plt.tight_layout()` | Automatically adjusts spacing between subplots. | `plt.tight_layout()` |
| `plt.savefig()` | Saves the figure to a file. | `plt.savefig("plot.png")` |
| `plt.show()` | Displays the figure. | `plt.show()` |

---

# Choosing the Right Chart

Choosing the correct visualization is as important as building the right machine learning model.

| Goal | Recommended Chart |
|------|-------------------|
| Show trends over time | Line Plot |
| Compare categories | Bar Chart |
| Compare many categories with long labels | Horizontal Bar Chart |
| Show relationships between two variables | Scatter Plot |
| Display the distribution of numerical values | Histogram |
| Detect outliers | Box Plot |
| Show proportions | Pie Chart (only for a small number of categories) |
| Compare multiple visualizations | Subplots |

---

# Matplotlib in the Data Science Workflow

Matplotlib is commonly used during the **Exploratory Data Analysis (EDA)** phase of a machine learning project.

Typical workflow:

1. Load the dataset with Pandas.
2. Inspect the data.
3. Visualize numerical variables.
4. Detect missing values and outliers.
5. Understand relationships between variables.
6. Perform feature engineering if necessary.
7. Prepare the data for model training.

Example:

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("data.csv")

plt.figure(figsize=(8,5))
plt.hist(df["Age"])
plt.title("Age Distribution")
plt.xlabel("Age")
plt.ylabel("Frequency")
plt.grid(True)

plt.show()
```

---

# Mini Project

Suppose you have a dataset containing laptop prices.

Using Matplotlib, you could answer questions such as:

- What is the distribution of laptop prices?
- Which company sells the most laptops?
- Is there a relationship between RAM and price?
- How are laptop weights distributed?
- Which operating system appears most frequently?

Possible visualizations:

- Histogram → Laptop prices
- Bar Chart → Number of laptops by company
- Scatter Plot → RAM vs Price
- Box Plot → Price by operating system
- Line Plot → Average price by screen size

These visualizations help you understand the data before training a machine learning model.

---

# Key Takeaways

- Matplotlib is the foundation of data visualization in Python.
- It integrates seamlessly with NumPy and Pandas.
- Use the appropriate chart type for your data.
- Always label axes and provide informative titles.
- Keep visualizations simple, readable, and focused on the message you want to communicate.
