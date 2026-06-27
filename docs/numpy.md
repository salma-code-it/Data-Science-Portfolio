# NumPy Guide

## Table of Contents

1. Introduction
2. What is NumPy?
3. Why Do We Use NumPy?
4. Installation
5. Importing NumPy
6. NumPy Arrays
7. Why Arrays Instead of Python Lists?
8. Creating Arrays
9. Array Attributes
10. Data Types
11. Indexing and Slicing
12. Reshaping Arrays
13. Mathematical Operations
14. Statistical Operations
15. Random Module
16. Broadcasting
17. Advantages
18. Disadvantages
19. Best Practices
20. Common Beginner Mistakes
21. Summary

---

# 1. Introduction

NumPy (Numerical Python) is the fundamental library for numerical computing in Python. It provides powerful tools for working with arrays, matrices, and mathematical operations.

Many popular Data Science and Machine Learning libraries are built on top of NumPy, including:

* Pandas
* Scikit-learn
* Matplotlib
* SciPy
* TensorFlow
* PyTorch

Because of this, learning NumPy is an essential step before studying Machine Learning.

---

# 2. What is NumPy?

NumPy is an open-source Python library designed for fast numerical computation.

Its main feature is the **ndarray** (N-dimensional array), which stores data efficiently and allows mathematical operations to be performed much faster than standard Python lists.

NumPy is optimized using low-level implementations written primarily in C, making it significantly faster than pure Python for numerical tasks.

---

# 3. Why Do We Use NumPy?

Without NumPy, performing mathematical operations on large datasets would be slower and require more code.

NumPy helps us:

* Store numerical data efficiently.
* Perform vectorized operations.
* Work with matrices.
* Generate random numbers.
* Compute statistics.
* Perform linear algebra operations.

In Data Science, almost every dataset is eventually converted into a NumPy array.

---

# 4. Installation

Install NumPy using pip:

```bash
pip install numpy
```

Check the installation:

```bash
pip show numpy
```

Display the installed version:

```python
import numpy as np

print(np.__version__)
```

---

# 5. Importing NumPy

The standard convention is:

```python
import numpy as np
```

The alias `np` is widely used in tutorials, books, and professional projects.

---

# 6. NumPy Arrays

The main object provided by NumPy is the ndarray.

Example:

```python
import numpy as np

numbers = np.array([10,20,30,40])

print(numbers)
```

Output

```
[10 20 30 40]
```

Unlike Python lists, NumPy arrays store elements of the same data type in contiguous memory, making computations faster and more memory efficient.

---

# 7. Why Arrays Instead of Python Lists?

Python lists are flexible because they can contain different data types.

Example:

```python
my_list = [1, "Python", 3.5]
```

A NumPy array is designed for numerical computing and generally stores elements of the same type.

```python
numbers = np.array([1,2,3,4])
```

Comparison:

| Feature                       | Python List | NumPy Array |
| ----------------------------- | ----------- | ----------- |
| Speed                         | Slower      | Faster      |
| Memory usage                  | Higher      | Lower       |
| Mathematical operations       | Limited     | Excellent   |
| Suitable for Machine Learning | No          | Yes         |

---

# 8. Creating Arrays

One-dimensional array

```python
arr = np.array([1,2,3,4])
```

Two-dimensional array

```python
arr = np.array([
    [1,2],
    [3,4]
])
```

Array filled with zeros

```python
np.zeros((3,3))
```

Array filled with ones

```python
np.ones((2,4))
```

Identity matrix

```python
np.eye(4)
```

Range of values

```python
np.arange(0,10,2)
```

Evenly spaced values

```python
np.linspace(0,1,5)
```

Random values

```python
np.random.rand(3,3)
```

---

# 9. Array Attributes

Example

```python
arr = np.array([[1,2,3],[4,5,6]])
```

Shape

```python
arr.shape
```

Number of dimensions

```python
arr.ndim
```

Total number of elements

```python
arr.size
```

Data type

```python
arr.dtype
```

Memory usage

```python
arr.nbytes
```

These attributes help you understand the structure and storage of your data.

---

# 10. Data Types

Common NumPy data types include:

* int32
* int64
* float32
* float64
* bool
* complex

Convert a data type:

```python
arr.astype(float)
```

Choosing an appropriate data type can reduce memory usage and improve performance.

---

# 11. Indexing and Slicing

Access one element

```python
arr[0]
```

Access multiple elements

```python
arr[1:4]
```

Two-dimensional indexing

```python
matrix[1,2]
```

Slice rows

```python
matrix[:,1]
```

Slice columns

```python
matrix[0,:]
```

---

# 12. Reshaping Arrays

Example

```python
arr = np.arange(12)

arr.reshape(3,4)
```

Flatten

```python
arr.flatten()
```

Transpose

```python
arr.T
```

Reshaping is commonly used before training machine learning models.

---

# 13. Mathematical Operations

Addition

```python
arr + 10
```

Subtraction

```python
arr - 5
```

Multiplication

```python
arr * 2
```

Division

```python
arr / 3
```

Power

```python
arr ** 2
```

Square root

```python
np.sqrt(arr)
```

These operations are vectorized, meaning they are applied to every element without writing loops.

---

# 14. Statistical Operations

Mean

```python
arr.mean()
```

Median

```python
np.median(arr)
```

Maximum

```python
arr.max()
```

Minimum

```python
arr.min()
```

Standard deviation

```python
arr.std()
```

Variance

```python
arr.var()
```

Sum

```python
arr.sum()
```

---

# 15. Random Module

Random integer

```python
np.random.randint(0,100)
```

Random array

```python
np.random.rand(5)
```

Normal distribution

```python
np.random.randn(100)
```

Random numbers are frequently used for simulations, testing, and initializing machine learning models.

---

# 16. Broadcasting

Broadcasting allows NumPy to perform operations on arrays with different shapes without manually resizing them.

Example

```python
arr = np.array([1,2,3])

arr + 5
```

Output

```
[6 7 8]
```

Broadcasting makes code shorter, faster, and easier to read.

---

# 17. Advantages

* Very fast numerical computation.
* Memory efficient.
* Excellent support for vectorized operations.
* Foundation of the Python Data Science ecosystem.
* Supports linear algebra and scientific computing.
* Easy integration with Pandas and Scikit-learn.

---

# 18. Disadvantages

* Primarily designed for numerical data.
* Less convenient than Pandas for labeled tabular data.
* Arrays usually require a single data type.
* Can have a learning curve for advanced indexing and broadcasting.

---

# 19. Best Practices

* Import NumPy as `np`.
* Prefer vectorized operations instead of Python loops.
* Choose appropriate data types to reduce memory usage.
* Avoid unnecessary copies of arrays.
* Use built-in NumPy functions instead of implementing mathematical operations manually.

---

# 20. Common Beginner Mistakes

Using Python loops instead of vectorized operations.

Using lists instead of arrays for numerical computation.

Ignoring array shapes before training models.

Mixing incompatible data types.

Forgetting that many NumPy operations return a new array rather than modifying the original one.

---

# 21. Summary

NumPy is the foundation of numerical computing in Python.

Understanding arrays, mathematical operations, indexing, broadcasting, and statistics is essential before learning Pandas, Scikit-learn, or Deep Learning frameworks.

Mastering NumPy will make your Machine Learning code faster, cleaner, and more efficient.
