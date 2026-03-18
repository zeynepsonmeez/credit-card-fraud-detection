# Credit Card Fraud Detection

## Overview
This project focuses on detecting fraudulent credit card transactions using machine learning techniques.

This is my first end-to-end machine learning project, where I applied data analysis, preprocessing, and model evaluation techniques on a real-world dataset.

---

## Dataset
The dataset is from Kaggle and contains anonymized credit card transactions.

It is highly imbalanced, with a very small percentage of fraud cases compared to normal transactions.

Dataset is not included in this repository due to size.

---

## Problem
Detect fraudulent transactions in a highly imbalanced dataset.

This is a challenging problem because traditional metrics like accuracy can be misleading.

---

## Approach
- Exploratory Data Analysis (EDA)
- Data preprocessing and feature scaling
- Handling imbalanced data using class weights
- Model training and evaluation
- Model comparison

---

## Models Used
- Logistic Regression
- Random Forest

---

## Evaluation Metrics
- Precision
- Recall
- F1 Score
- ROC-AUC

Accuracy was not considered sufficient due to class imbalance.

---

## Results

### Logistic Regression
- High recall
- Very low precision
- Detects most fraud cases but produces many false positives

### Random Forest
- High precision
- Lower recall
- Produces fewer false positives but misses some fraud cases

---

## Conclusion
There is a trade-off between precision and recall in fraud detection.

- Logistic Regression is better when the goal is to detect as many fraud cases as possible.
- Random Forest is better when the goal is to reduce false alarms.

The choice of model depends on the business objective.

---

## Technologies
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

---

## Future Improvements
- Apply SMOTE for better handling of imbalanced data
- Try advanced models like XGBoost
- Perform hyperparameter tuning
- Optimize classification threshold
