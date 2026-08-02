# Clinical Data Science | Predicting Glycated Hemoglobin with Machine Learning

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Library-Scikit_Learn-orange.svg)](https://scikit-learn.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## Project Overview

This project investigates whether routinely collected clinical and anthropometric measurements can be used to predict **glycated hemoglobin (HbA1c)** through Machine Learning techniques.

The repository documents the complete workflow of a supervised regression problem, covering:

- Exploratory Data Analysis (EDA)
- Data cleaning and preprocessing
- Clinical feature engineering
- Model training and evaluation
- Hyperparameter optimization
- Feature importance analysis

Particular attention is devoted to **preventing data leakage**, ensuring that every data-driven transformation is performed exclusively on the training set.

---

## Dataset

The dataset contains demographic, anthropometric and laboratory measurements collected from patients, including:

- Age
- Gender
- Height and Weight
- Waist and Hip Circumference
- Blood Pressure
- Cholesterol Profile
- Stable Glucose
- Glycated Hemoglobin (Target Variable)

The objective is to predict **HbA1c (`glyhb`)**, an important biomarker used in diabetes diagnosis and long-term glucose monitoring.

---

## Methodological Pipeline

The project follows a modular pipeline designed to mirror a real-world Machine Learning workflow.

1. **Exploratory Data Analysis (EDA)**
   - Missing value analysis
   - Distribution analysis
   - Outlier detection
   - Correlation analysis
   - Clinical interpretation of variables

2. **Train-Test Split**
   - Data are split before any statistical transformation to avoid information leakage.

3. **Feature Engineering**
   Creation of clinically meaningful features, including:

   - Body Mass Index (BMI)
   - Waist-to-Hip Ratio (WHR)
   - Mean Arterial Pressure (MAP)
   - Pulse Pressure (PP)
   - Polynomial features and interaction terms

4. **Preprocessing**
   - Missing value imputation (`KNNImputer`)
   - Feature scaling
   - Pipeline-based transformations

5. **Model Development**
   - Random Forest Regressor
   - K-Fold Cross Validation
   - Hyperparameter optimization using `RandomizedSearchCV`

6. **Feature Selection**
   - Model-based importance analysis (`feature_importances_`)
   - Removal of low-informative variables

---

## Main Results

**Final Model**

- Random Forest Regressor
- Hyperparameter optimization with `RandomizedSearchCV`

**Performance on the Test Set**

- **Mean Squared Error (log scale):** ~0.0425
- **R² Score:** ~0.54

The obtained performance indicates that routinely available clinical measurements explain over half of the variability in glycated hemoglobin levels.

Although the prediction cannot fully capture the complexity of diabetes progression, the results demonstrate that meaningful predictive information can be extracted from standard clinical and anthropometric measurements.

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

Clone the repository

```bash
git clone https://github.com/your-username/diabetes-ml-prediction.git
cd diabetes-ml-prediction
```

Install the required dependencies

```bash
pip install -r requirements.txt
```

Run the notebooks in numerical order.

The project is compatible with both **Google Colab** and **local Python environments**, using dynamic paths managed through `pathlib`.

---

## Tech Stack

**Programming Language**

- Python 3.8+

**Data Analysis**

- Pandas
- NumPy

**Visualization**

- Matplotlib
- Seaborn

**Machine Learning**

- Scikit-Learn

**Statistical Analysis**

- Statsmodels

---

## Skills Demonstrated

- Exploratory Data Analysis (EDA)
- Missing Data Analysis
- Clinical Feature Engineering
- Data Leakage Prevention
- Machine Learning Regression
- Hyperparameter Optimization
- Cross Validation
- Model Evaluation
- Feature Importance Analysis

---

## Future Improvements

Potential extensions of this project include:

- Comparison with Gradient Boosting models (XGBoost, LightGBM)
- SHAP analysis for model interpretability
- Recursive Feature Elimination (RFE)
- Stacking and ensemble methods
- Deployment as an interactive web application
