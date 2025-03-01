# Predicting Mental Health Outcomes in Chronic Disease Patients

This project aims to predict mental health outcomes in chronic disease patients using machine learning. The goal is to provide early warnings about potential mental health issues, enabling healthcare providers to intervene sooner and improve patient care.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Features](#features)
- [Data Preprocessing](#data-preprocessing)
- [Model Training](#model-training)
- [Prediction](#prediction)
- [Explainability](#explainability)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction
Predictive analytics can transform healthcare by providing insights and early warnings about potential mental health issues in chronic disease patients. This project leverages machine learning to predict follow-up PHQ-9 scores based on various features related to patient demographics, disease severity, and lifestyle factors.

## Dataset
The dataset used in this project includes the following features:
- `Age`: Age of the patient
- `Chronic_Disease_Type`: Type of chronic disease (Heart Disease, Arthritis, Kidney Disease, Diabetes)
- `Disease_Severity`: Severity of the chronic disease (Mild, Moderate, Severe)
- `Duration_of_Illness_Years`: Duration of illness in years
- `Diet_Quality`: Quality of diet (Poor, Average, Good)
- `Exercise_Frequency_Per_Week`: Frequency of exercise per week
- `Social_Engagement`: Level of social engagement (Low, Medium, High)
- `Sleep_Quality`: Quality of sleep (Poor, Average, Good)
- `Symptoms`: Symptoms experienced (Mild Stress, Mild Anxiety, Mild Depression, etc.)
- `Demographic_Info`: Demographic information (Single, Married, Divorced, Unemployed, Employed)
- `Baseline_PHQ9_Score`: Baseline PHQ-9 score
- `Followup_PHQ9_Score`: Follow-up PHQ-9 score (Target Variable)

## Features
### Domain-Specific Mapping for Categorical Columns
**Chronic Disease Type::** Heart Disease: 1, Arthritis: 2, Kidney Disease: 3, Diabetes: 4  
**Disease Severity::** Mild: 0, Moderate: 1, Severe: 2  
**Diet Quality::** Poor: 0, Average: 1, Good: 2  
**Exercise Frequency Per Week::** Numerical values representing the frequency (e.g., 0, 1, 2, ... 7)  
**Social Engagement::** Low: 0, Medium: 1, High: 2  
**Sleep Quality::** Poor: 0, Average: 1, Good: 2  
**Symptoms::** Mild Stress: 1, Mild Anxiety: 2, Mild Depression: 3, Moderate Stress: 11, Moderate Anxiety: 12, Moderate Depression: 13, Severe Stress: 21, Severe Anxiety: 22, Severe Depression: 23  
**Demographic Info::** Single: 1, Married: 2, Divorced: 3, Unemployed: 4, Employed: 5  
**Follow-up PHQ-9 Score (Target Variable)::** Minimal: 0, Mild: 1, Moderate: 2, Moderately Severe: 3, Severe: 4  

## Data Preprocessing
The categorical data is mapped to numerical values to make them suitable for machine learning models. Missing values are handled appropriately, and data is standardized where necessary.

## Model Training
A Random Forest classifier is used for prediction. The model is fine-tuned using GridSearchCV to find the best hyperparameters.

## Prediction
To make a prediction, ensure the input features are in the correct order. Here is an example:
```python
import pandas as pd

# Example input data including Baseline_PHQ9_Score
new_patient_data = {
    'Age': 55,
    'Chronic_Disease_Type': 3,
    'Disease_Severity': 2,
    'Duration_of_Illness_Years': 10,
    'Diet_Quality': 2,
    'Exercise
