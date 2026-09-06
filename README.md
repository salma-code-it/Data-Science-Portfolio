# Data Science Portfolio

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python">
  <img src="https://img.shields.io/badge/Machine%20Learning-Scikit--Learn-orange?style=for-the-badge">
  <img src="https://img.shields.io/badge/Data%20Science-Pandas-green?style=for-the-badge">
  <img src="https://img.shields.io/badge/Visualization-Matplotlib-red?style=for-the-badge">
</p>

---

# About This Repository

Welcome to my **Data Science Portfolio**.

This repository contains my Data Science and Machine Learning projects, along with detailed explanations of the tools, libraries, and workflows used throughout each project.

The primary goal of this repository is to document my learning journey while building real-world machine learning applications. Every project follows industry best practices, including data preprocessing, exploratory data analysis, feature engineering, model training, evaluation, and model serialization.

This portfolio is designed for:

- Students learning Data Science
- Machine Learning beginners
- Recruiters reviewing my work
- Developers interested in Python and AI
- Anyone looking for practical Machine Learning examples

---

# Objectives

The purpose of this repository is to:

- Practice Data Science with real datasets
- Build complete Machine Learning pipelines
- Learn data preprocessing techniques
- Compare different Machine Learning algorithms
- Improve Python programming skills
- Create reusable projects for future applications
- Build a professional portfolio for freelance opportunities and job applications

---

# 📂 Repository Structure

```text
obesity problem
│
├── ipynbfile/
├── raw_csv/
├── clean_csv/
├── models/
```

---

# Machine Learning Workflow

Every Machine Learning project in this repository follows a complete workflow.

```
Business Understanding
        ↓
Data Collection
        ↓
Exploratory Data Analysis
        ↓
Data Cleaning
        ↓
Feature Engineering
        ↓
Model Selection
        ↓
Model Training
        ↓
Model Evaluation
        ↓
Model Saving
        ↓
Deployment
```

Following a structured workflow helps produce reliable, reproducible, and maintainable machine learning solutions.

---

# Python Virtual Environment

## What is a Virtual Environment?

A virtual environment is an isolated Python environment that allows a project to have its own dependencies without affecting the global Python installation.

Each project can use different library versions independently.

For example:

- Project A may use Pandas 2.0
- Project B may use Pandas 1.5

Both projects can coexist without conflicts.

---

## Why Do We Use a Virtual Environment?

Using a virtual environment provides several advantages:

- Prevents dependency conflicts
- Keeps projects isolated
- Makes projects reproducible
- Simplifies collaboration
- Avoids modifying the system-wide Python installation

Without a virtual environment, installing or upgrading packages for one project may accidentally break another project.

---

# 🛠 Creating a Virtual Environment

Windows / Linux / macOS

```bash
python -m venv venv
```

or

```bash
python3 -m venv venv
```

This command creates a folder named **venv** containing a separate Python interpreter and package manager.

---

# Activate the Virtual Environment

## Windows

```bash
venv\Scripts\activate
```

After activation, your terminal will look similar to:

```text
(venv) C:\Users\Username\Project>
```

---

## Linux / macOS

```bash
source venv/bin/activate
```

---

# ⛔ Deactivate the Environment

When you finish working, simply run:

```bash
deactivate
```

This returns your terminal to the global Python environment.

---

# Installing Python Libraries

To install a package:

```bash
pip install package_name
```

Example:

```bash
pip install pandas
```

To install multiple packages:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

---

# Uninstall a Library

```bash
pip uninstall package_name
```

Example:

```bash
pip uninstall pandas
```

---

# 📋 Display Installed Libraries

Show all installed packages:

```bash
pip list
```

Show detailed information about a package:

```bash
pip show pandas
```

Example output includes:

- Package version
- Installation path
- Dependencies
- Summary
- Author information

---

# Export Installed Libraries

After completing a project, save all installed packages into a file:

```bash
pip freeze > requirements.txt
```

Example:

```text
numpy==2.1.1
pandas==2.2.2
matplotlib==3.9.0
scikit-learn==1.6.0
```

This file allows others to recreate the same environment.

---

# Install Libraries from requirements.txt

Instead of installing each package manually:

```bash
pip install -r requirements.txt
```

This automatically installs every required dependency.

---

# 🧩 Using Jupyter Notebook

When opening a notebook (`.ipynb`), always verify that the correct virtual environment is selected as the notebook kernel.

Using the wrong kernel may result in missing packages or unexpected behavior.

---

# 🐍 Finding the Current Python Interpreter

Sometimes you may have multiple Python installations on your computer.

To determine which Python interpreter is currently running:

```python
import sys

print(sys.executable)
```

Example output:

```text
C:\Users\Salma\DataSciencePortfolio\venv\Scripts\python.exe
```

If this path points to your virtual environment, your notebook is correctly configured.

---

#  What is the `sys` Module?

The `sys` module is a built-in Python library that provides access to variables and functions used by the Python interpreter.

Unlike external libraries, it does not require installation.

Simply import it:

```python
import sys
```

---

## Common Uses of `sys`

### Find the Python executable

```python
print(sys.executable)
```

Returns the full path of the active Python interpreter.

---

### Check the Python version

```python
print(sys.version)
```

Example:

```text
3.11.5
```

---

### Display command-line arguments

```python
print(sys.argv)
```

Useful for creating command-line applications.

---

### Exit a Python program

```python
sys.exit()
```

Stops the execution of the current program.

---

# 🌍 Kaggle

## What is Kaggle?

Kaggle is one of the world's largest online communities for Data Science and Machine Learning.

It provides thousands of public datasets, interactive notebooks, educational courses, and machine learning competitions.

Whether you are a beginner or an experienced data scientist, Kaggle offers valuable resources for learning and practicing real-world data analysis.

---

## Why Use Kaggle?

Kaggle allows you to:

- Download real-world datasets
- Practice machine learning
- Participate in competitions
- Learn from public notebooks
- Explore data visualizations
- Improve data preprocessing skills
- Compare your solutions with other data scientists

---

## Types of Resources Available

### Datasets

Thousands of datasets are available in areas such as:

- Healthcare
- Finance
- Education
- Sports
- Climate
- Agriculture
- Marketing
- Business
- Computer Vision
- Natural Language Processing

Most datasets are provided in CSV format, although JSON, SQLite, Parquet, Excel, and image datasets are also available.

---

### Kaggle Learn

Kaggle offers free courses covering topics such as:

- Python
- Pandas
- Data Visualization
- SQL
- Intro to Machine Learning
- Intermediate Machine Learning
- Feature Engineering
- Deep Learning
- Computer Vision
- Natural Language Processing

These courses are beginner-friendly and include practical exercises.

---

### 🏆 Competitions

Competitions challenge participants to solve real-world machine learning problems.

Examples include:

- House Price Prediction
- Titanic Survival Prediction
- Image Classification
- Fraud Detection
- Medical Diagnosis

They help improve problem-solving skills and expose you to industry-level datasets.

---

### 📒 Kaggle Notebooks

Kaggle Notebooks allow you to write and execute Python code directly in your browser without installing any software.

They come with pre-installed libraries such as:

- NumPy
- Pandas
- Scikit-learn
- TensorFlow
- PyTorch
- Matplotlib
- Seaborn

---

## Example Dataset

One of the datasets used in this repository is the **Obesity Risk Dataset**.

Dataset:

https://www.kaggle.com/datasets/jpkochar/obesity-risk-dataset

This dataset is used to build machine learning models that classify obesity risk based on lifestyle and health-related features.

---

# Best Practices

✔ Always create a virtual environment before starting a new project.

✔ Keep your `requirements.txt` file updated.

✔ Use descriptive folder names.

✔ Document every project with a README.

✔ Save trained models instead of retraining them every time.

✔ Use Git for version control.

✔ Write clean and well-commented code.

✔ Keep datasets separate from source code.

---

# What's Next?

The next section of this documentation covers the most important Python libraries used in Data Science:

- NumPy
- Pandas
- Matplotlib
- Seaborn

Each library will include:

- What it is
- Why it is used
- Advantages
- Disadvantages
- Practical examples
- Best practices
