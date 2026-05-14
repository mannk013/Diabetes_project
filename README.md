# Diabetes Prediction — Machine Learning Project

## Overview
End-to-end machine learning project to predict diabetes in patients using the Pima Indians Diabetes Dataset. The project follows the **OSEMN framework** (Obtain, Scrub, Explore, Model, Interpret).

## Dataset
- **Source:** [Pima Indians Diabetes Database — Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
- **Size:** 768 patients, 9 features
- **Target:** Outcome (0 = healthy, 1 = diabetic)

## OSEMN Framework

###  Obtain
- Loaded dataset using pandas `read_csv()`

###  Scrub
- Identified medically impossible zero values in: Glucose, BloodPressure, SkinThickness, Insulin, BMI
- Replaced zeros with `NaN` and imputed using **median** (robust to outliers)
- Result: 0 missing values after cleaning

###  Explore
- Discovered **class imbalance**: 65% healthy vs 35% diabetic
- Correlation heatmap revealed **Glucose** as strongest predictor (0.49)
- BMI and Age identified as second and third strongest predictors

###  Model
Trained and compared two models:

| Model | Accuracy | Diabetic Recall | AUC |
|-------|----------|-----------------|-----|
| Logistic Regression | 75.3% | 0.62 | 0.82 |
| **Random Forest** | 74.7% | **0.67** | **0.83** |

###  Interpret
- **Glucose** is by far the most important feature (importance score ~0.26)
- **BMI** and **Age** follow as second and third most important
- Random Forest preferred in medical context — higher recall means fewer missed diabetic patients

## Key Findings
- Glucose level is the single strongest predictor of diabetes
- A model with high recall is preferred over high accuracy in medical diagnosis
- Class imbalance must be considered — accuracy alone is misleading

## Tech Stack
- Python 3.13
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn

## Project Structure
```
diabetes_project/
│
├── data/
│   └── diabetes.csv
├── notebook.ipynb
└── README.md
```

## How to Run
```bash
git clone https://github.com/YOUR_USERNAME/diabetes_project
cd diabetes_project
pip install pandas numpy matplotlib seaborn scikit-learn
jupyter notebook
```