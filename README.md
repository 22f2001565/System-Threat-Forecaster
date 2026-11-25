# System-Threat-Forecaster

A machine learning pipeline that predicts whether a system is likely to be infected by malware, based on different properties of the system. Built for the Machine Learning Practice Project, Term 1 2025, as part of the IIT Madras BS in Data Science and Applications. 

## Problem Statement

The data comes from telemetry collected by antivirus software on user systems. Each row describes one system through 70+ properties, and the task is to predict whether that system was infected (binary classification). Submissions are scored on accuracy between the predicted and true classes.

## Approach

1. **Exploratory data analysis:** Checked missing values, feature distributions, correlations (heatmap) and outliers (box plots, z-scores).
2. **Data preprocessing:**
   - Dropped the `MachineID` identifier column
   - Encoded categorical features with `OrdinalEncoder` (unseen categories in test data mapped to -1)
   - Imputed missing numeric values with the median and standardized them with `StandardScaler`
   - Split the data 90/10 into training and validation sets
3. **Models compared:**
   - Logistic Regression
   - SGD Classifier
   - Random Forest
   - XGBoost
   - LightGBM
4. **Hyperparameter tuning:** `RandomizedSearchCV` with 3-fold cross-validation for SGD, XGBoost and LightGBM

## Tech Stack

Python, pandas, NumPy, scikit-learn, XGBoost, LightGBM
