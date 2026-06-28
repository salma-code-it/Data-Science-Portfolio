# 18. Box Plot

A Box Plot summarizes the distribution of numerical data and helps detect outliers.

It displays:

- Minimum value
- First Quartile (Q1)
- Median
- Third Quartile (Q3)
- Maximum value
- Outliers

Example

```python
sns.boxplot(
    data=df,
    x="Gender",
    y="Salary"
)

plt.show()
```

Common applications:

- Detecting outliers
- Comparing distributions between groups
- Checking data spread

---

# 19. Violin Plot

A Violin Plot combines a Box Plot with a density plot.

It shows:

- Distribution
- Density
- Median
- Quartiles

Example

```python
# Violinplot
plt.figure(figsize=(12,5))
plt.subplot(1,2,1)
sns.violinplot(data=iris, x="species", y="sepal_length")
plt.title("Violin Plot")

# Boxplot
plt.subplot(1,2,2)
sns.boxplot(data=iris, x="species", y="sepal_length")
plt.title("Box Plot")

plt.show()
```
<img width="988" height="470" alt="image" src="https://github.com/user-attachments/assets/66acb329-a1bb-4794-9f88-82c72987b3d6" />


Use a Violin Plot when you want to understand the shape of the data distribution, not just summary statistics.

---

# 20. Pair Plot

A Pair Plot automatically creates scatter plots between numerical variables.

Example

```python
sns.pairplot(iris)

plt.show()
```
<img width="986" height="986" alt="image" src="https://github.com/user-attachments/assets/e2dbbbf6-6e0c-40e1-92b6-663791ee5c81" />
What each plot shows
Diagonal plots → histograms of a single variable (sepal_length, sepal_width, petal_length, petal_width). They show the distribution of values for that feature.

Off-diagonal plots → scatterplots comparing two variables. For example:

sepal_length vs sepal_width → shows how sepal length relates to sepal width.

sepal_length vs petal_length → shows correlation between sepal length and petal length.

petal_length vs petal_width → shows a strong positive correlation (points form a diagonal line).


Color by category:

```python
sns.pairplot(
    df,
    hue="Species"
)

plt.show()
```

Applications:

- Finding relationships between variables
- Detecting clusters
- Detecting outliers
- Exploring datasets before training models

---

# 21. Heatmap

A Heatmap represents values using colors.

One of its most common uses is displaying a correlation matrix.

Example

```python
correlation = iris.corr(numeric_only=True)

sns.heatmap(correlation)

plt.show()
```
<img width="527" height="418" alt="image" src="https://github.com/user-attachments/assets/60ebdbb3-248c-4a07-8c38-485e445d9444" />

With annotations

```python
sns.heatmap(
    correlation,
    annot=True,
    cmap="coolwarm"
)

plt.show()
```
<img width="527" height="418" alt="image" src="https://github.com/user-attachments/assets/91c8aad3-633d-48f1-a4f1-046730017277" />

Applications:

- Correlation analysis
- Feature selection
- Identifying highly correlated variables

---

# 22. Regression Plot

Regression plots visualize the relationship between two numerical variables and add a fitted regression line.

Example

```python
sns.regplot(
    data=df,
    x="Age",
    y="Salary"
)

plt.show()
```

Applications:

- Linear relationships
- Trend analysis
- Exploratory Data Analysis

---

# 23. Color Palettes

Seaborn provides built-in color palettes.

Example

```python
sns.set_palette("deep")
```

Other common palettes:

- deep
- muted
- bright
- pastel
- dark
- colorblind

Choose palettes that improve readability and accessibility.

---

# 24. Advantages

- Easy to learn.
- Beautiful default visualizations.
- Built on top of Matplotlib.
- Works directly with Pandas DataFrames.
- Excellent for Exploratory Data Analysis.
- Requires less code than Matplotlib.
- Strong community support.

---

# 25. Disadvantages

- Less flexible than Matplotlib for advanced customization.
- Some visualizations become slow on very large datasets.
- Depends on Matplotlib for rendering.

---

# 26. Best Practices

Use Seaborn during Exploratory Data Analysis.

Choose the correct chart for your data.

Always label your axes.

Use meaningful titles.

Avoid unnecessary colors.

Keep charts simple and easy to understand.

Use Heatmaps to analyze feature correlations before model training.

---

# 27. Common Beginner Mistakes

Using the wrong chart type.

Not checking for missing values before plotting.

Creating overcrowded visualizations.

Ignoring axis labels.

Using too many colors.

Interpreting correlation as causation.

---

# 28. Frequently Used Functions

| Function | Purpose |
|----------|---------|
| `sns.lineplot()` | Line chart |
| `sns.scatterplot()` | Scatter plot |
| `sns.barplot()` | Bar chart |
| `sns.countplot()` | Count categories |
| `sns.histplot()` | Histogram |
| `sns.kdeplot()` | Density curve |
| `sns.displot()` | Distribution plot |
| `sns.boxplot()` | Box plot |
| `sns.violinplot()` | Violin plot |
| `sns.pairplot()` | Pair plot |
| `sns.heatmap()` | Heatmap |
| `sns.regplot()` | Regression plot |
| `sns.set_theme()` | Apply theme |
| `sns.set_style()` | Change style |
| `sns.set_palette()` | Change color palette |

---

# 29. Choosing the Right Plot

| Goal | Recommended Plot |
|------|------------------|
| Compare categories | Bar Plot |
| Count categories | Count Plot |
| Show trends | Line Plot |
| Relationship between two variables | Scatter Plot |
| Distribution of values | Histogram |
| Smooth distribution | KDE Plot |
| Detect outliers | Box Plot |
| Distribution by category | Violin Plot |
| Correlation between features | Heatmap |
| Explore multiple variables | Pair Plot |

---

# 30. Summary

Seaborn is one of the most important visualization libraries for Data Science.

It simplifies the creation of statistical graphics while producing attractive and informative visualizations with minimal code.

Combined with Pandas and Matplotlib, Seaborn enables efficient exploratory data analysis, helping data scientists understand datasets before applying machine learning algorithms.
