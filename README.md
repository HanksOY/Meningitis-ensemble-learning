Machine Learning for Early Detection of Meningitis:
A stacked ensemble learning framework for predicting meningitis in ER and ICU patients using MIMIC-III electronic health record data.

Overview
This project implements an advanced machine learning approach to identify meningitis risk early from structured EHR data. The model achieves exceptional performance (AUC: 0.9637 on standard testing, 0.9472 on challenging diagnostic scenarios) by combining Random Forest, LightGBM, and Deep Neural Networks through ensemble learning.
Key Features

Stacked Ensemble Learning: Combines three base models (Random Forest, LightGBM, DNN) with a logistic regression meta-learner
Rigorous Feature Engineering: Two-stage feature selection identifying clinically relevant risk factors including gender and high-risk ICD codes
Class Imbalance Handling: Sophisticated undersampling techniques to address the 0.46% meningitis prevalence rate
Dual Testing Framework:

Testing Set 1: Standard balanced evaluation (34 meningitis + 34 regular non-meningitis samples)
Testing Set 2: Challenging diagnostic scenario with confounding risk features



Dataset

Source: MIMIC-III v1.4 database
Cohort: 214 meningitis cases and 46,303 non-meningitis controls from ICU admissions (2001-2012)
Features: 6,962 variables including demographics, ICD-9 diagnostic codes, and procedures

Model Performance
Testing Set 1 (Standard)

AUC: 0.9637
Sensitivity: 0.9377
Specificity: 0.9101
F1-Score: 0.9242

Testing Set 2 (Challenging)

AUC: 0.9472
Sensitivity: 0.9377
Specificity: 0.7917
F1-Score: 0.8723

Implementation
The notebook includes:

Data preprocessing and ICD-based cohort selection
One-hot encoding of diagnostic codes
5-fold stratified cross-validation
Base model training (Random Forest, LightGBM, DNN)
Meta-model stacking with logistic regression
Comprehensive evaluation metrics with 95% confidence intervals

Top Risk Features
Key identified risk factors include:

Gender
Coronary atherosclerosis (414.01)
Obstructive hydrocephalus (331.4)
Subarachnoid hemorrhage (430)
Secondary malignant neoplasm of brain (198.3)
Intracerebral hemorrhage (431)

Requirements

Python 3.x
scikit-learn
LightGBM
PyTorch
pandas
numpy

Citation
If you use this work, please cite:
Ouyang, H., Hamilton, J., & Amal, S. (2025). Machine Learning for Early Detection of Meningitis: 
Stacked Ensemble Learning with EHR Data.

Author
Han Ouyang
Khoury College of Computer Science, The Roux Institute, Northeastern University

License
This project uses the MIMIC-III database, which requires credentialed access through PhysioNet.
