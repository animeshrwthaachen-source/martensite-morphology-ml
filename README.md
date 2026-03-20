# martensite-morphology-ml
# Machine learning based classification model for distinguishing different martensite morphologies

Hello! This repository contains the code I used to train and compare machine learning models for predicting *Martensite morphology* from processing and microstructural features.

The main goal of this work is to see how well different ML (classification) models can classify martensite morphology and to understand which input features are most influential in the prediction.

# What this project does ? 

This project:

- loads the martensite morphology dataset 
- preprocesses the data
- encodes the target labels
- splits the data into training and test sets
- performs hyperparameter tuning using */*5-fold cross-validation*/*
- trains three machine learning models:
  - Logistic Regression
  - Random Forest
  - XGBoost
- evaluates the final models on the test set
- visualizes:
  - model accuracy
  - confusion matrices
  - train vs test performance
  - feature importance
  - overall performance metrics

## Aim of the work?

Martensite morphology is strongly linked to the final properties of steel, so being able to predict it from processing and microstructural parameters can be helpful for both materials understanding and data-driven alloy/process design.

This repository was created to keep the code organized, reproducible, and easy to share alongside the paper.

# Files in this repository

- `martensite_morphology_models.py`  
  Main Python script containing the full workflow

- `requirements.txt`  
  Required Python packages

- `data/ML-Martensite Morphology-2.csv`  
  Dataset used for training and testing  
  *(for the data reders need to request it from the authors beforehand and load it into the same folder of model file) )*

## Models used

Three models are compared in this work:

## 1. Logistic Regression ##
A simple and interpretable baseline model.  
Useful for checking whether the classes can be separated with a relatively simple decision boundary.

## 2. Random Forest ##
An ensemble tree-based model that can capture nonlinear relationships and interactions between features.

### 3. XGBoost ##
A boosted tree model that often performs very well on structured/tabular datasets.

## Method overview

The workflow used in this repository is:

1. Read the dataset from CSV
2. Clean column names
3. Separate features and target
4. Encode the target labels numerically
5. Split the dataset into training and test sets
6. Define model pipelines
7. Perform hyperparameter tuning using `GridSearchCV` with 5-fold cross-validation
8. Select the best model settings
9. Evaluate the best models on the test set
10. Plot results for interpretation

## Reproducibility

A fixed random seed is used in the code:

```python
SEED = 42
