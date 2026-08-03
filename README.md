# Clinical Data Science | Predicting Glycated Hemoglobin with Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Library-Scikit_Learn-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Project Overview

This repository was developed as a personal Machine Learning project to practice the complete workflow of a supervised regression task using real clinical data.

The project investigates whether clinical measurements can be used to predict **glycated hemoglobin (HbA1c)** through Machine Learning techniques.

The repository documents the complete workflow of a supervised regression problem, covering:

- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Clinical feature engineering
- Model training and evaluation
- Hyperparameter optimization
- Feature importance analysis

---

## Dataset

The dataset contains general information and clinical measurements collected from patients, including:

- Age
- Gender
- Height and Weight
- Waist and Hip Circumference
- Blood Pressure
- Cholesterol Profile
- Stable Glucose
- Glycated Hemoglobin (Target Variable)

The objective is to predict **HbA1c (`glyhb`)**, an important biomarker used in diabetes diagnosis and long-term glucose monitoring.

Once HbA1c has been predicted through a regression model, patients can also be classified according to standard clinical thresholds:

- Healthy (HbA1c < 5.7)
- Pre-diabetic (5.7 ≤ HbA1c < 6.5)
- Diabetic (HbA1c ≥ 6.5)

The dataset used in this project was obtained from the public **[Diabetes Dataset](https://www.kaggle.com/datasets/imtkaggleteam/diabetes)** available on Kaggle.

---

## Methodological Pipeline

The project follows a modular pipeline designed to mirror a real-world Machine Learning workflow.

### 1. Exploratory Data Analysis (EDA)

- Missing value analysis
- Distribution analysis
- Outlier detection
- Correlation analysis
- Clinical interpretation of variables

### 2. Train-Test Split

Data are split before any statistical transformation to avoid information leakage.

### 3. Feature Engineering

Creation of clinically inspired features, including:

- Body Mass Index (BMI)
- Waist-to-Hip Ratio (WHR)
- Mean Arterial Pressure (MAP)
- Pulse Pressure (PP)
- Polynomial features (Age²) and interaction terms (Age × Chol)

### 4. Preprocessing

- Missing value imputation (`KNNImputer`)
- Feature scaling
- Pipeline-based transformations

### 5. Model Development

- Random Forest Regressor
- K-Fold Cross Validation
- Hyperparameter optimization using `RandomizedSearchCV`

### 6. Feature Selection

- Model-based importance analysis (`feature_importances_`)
- Removal of low-informative variables

---

## Main Results

### Final Model

- Random Forest Regressor
- Hyperparameter optimization with `RandomizedSearchCV`

### Performance on the Test Set

- **Mean Squared Error (log scale):** ~0.0425
- **R² Score:** ~0.54

The obtained performance indicates that routinely available clinical measurements explain over half of the variability in glycated hemoglobin levels.

The main goal of this project was not to achieve the highest possible predictive performance, but to build a complete end-to-end Machine Learning pipeline that resembles a real Data Science project.

---

## Repository Structure

```text
diabetes-ml-prediction/
│
├── data/                  # Raw and processed datasets
├── notebooks/             # Jupyter notebooks
├── images/                # Figures and plots
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation
```

---

## How to Run

Clone the repository:

```bash
git clone https://github.com/your-username/diabetes-ml-prediction.git
cd diabetes-ml-prediction
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Run the notebooks in the following order:

1. `diabetes_regression_EDA.ipynb`
2. `diabetes_regression_Preprocessing.ipynb`
3. `diabetes_regression_MLmodel.ipynb`

The project is compatible with both **Google Colab** and **local Python environments**.

Before running the notebooks, update the project folder path at the beginning of each notebook.

---

## Tech Stack

### Programming Language

- Python 3.8+

### Data Analysis

- Pandas
- NumPy

### Visualization

- Matplotlib
- Seaborn

### Machine Learning

- Scikit-Learn

### Statistical Analysis

- Statsmodels

---

## Future Improvements

Possible future improvements include:

- Comparing the Random Forest model with Gradient Boosting methods (XGBoost, LightGBM)
- Using SHAP to improve model interpretability
- Recursive Feature Elimination (RFE)
- Stacking and other ensemble methods
- Exploring additional engineered features, such as Age × Cholesterol