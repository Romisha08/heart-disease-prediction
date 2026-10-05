### CardioPredict — Heart Disease Risk Prediction System
Python • Scikit-learn • XGBoost • Pandas • Streamlit

```
Patient Data
     ↓
Data Cleaning
     ↓
Missing Value Handling
     ↓
EDA
     ↓
Train/Test Split
     ↓
Preprocessing
 ┌───────────────┐
 │ Encode Categorical
 │ Scale Numerical
 └───────────────┘
     ↓
 ┌───────────────┬───────────────┬───────────────┐
 │ Logistic Reg. │ Random Forest │   XGBoost     │
 └───────────────┴───────────────┴───────────────┘
     ↓
Compare Models
     ↓
Recall / Precision / F1 / ROC-AUC
     ↓
Confusion Matrix
     ↓
Select Best Model
     ↓
Save Pipeline
     ↓
Streamlit App
     ↓
Patient Input → Prediction

```

For a healthcare-oriented classifier, recall is especially important because a false negative means the model predicts "no disease" for someone whose target is positive. We will therefore report recall alongside precision, F1, accuracy and the confusion matrix rather than relying on accuracy alone.
# ❤️ Heart Disease Prediction System

## Overview

A machine learning classification system that predicts the
presence of heart disease using clinical patient information.

## Dataset

UCI Cleveland Heart Disease Dataset.

303 patient records and 13 clinical features.

## Features

- Age
- Sex
- Chest Pain Type
- Resting Blood Pressure
- Cholesterol
- Fasting Blood Sugar
- Resting ECG
- Maximum Heart Rate
- Exercise-Induced Angina
- ST Depression
- Slope
- Number of Major Vessels
- Thalassemia

## Machine Learning Models

1. Logistic Regression
2. Random Forest
3. XGBoost

## Preprocessing

- Missing value imputation
- One-hot encoding
- Standard scaling

## Evaluation

Models were compared using:

- Accuracy
- Precision
- Recall
- F1 Score
- ROC-AUC
- Confusion Matrix

Recall was given particular attention because false
negative predictions are especially important in this
classification setting.

## Deployment

The final model was deployed using Streamlit.

## Project Structure
```
heart-disease-prediction/
│
├── data/
├── notebooks/
├── artifacts/
├── app.py
├── requirements.txt
├── README.md
└── .gitignore
```
```
                 Heart Disease Dataset
                         │
                         ↓
                  ┌─────────────┐
                  │ Train 80%   │
                  └─────────────┘
                         │
              ┌──────────┴──────────┐
              ↓                     ↓
       Train models          Tune parameters
              │                     │
              └──────────┬──────────┘
                         ↓
                  Validation 10%
                         │
                  Select best model
                         ↓
                     Test 10%
                         │
                  FINAL evaluation
```

The critical principle is:
The test set should remain untouched until the very end.