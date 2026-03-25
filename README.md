# Credit Card Fraud Detection - V2

This repository documents the iterative development of my credit card fraud detection project while studying machine learning.

The project started as an initial notebook version and was later improved based on feedback, additional analysis, and a more structured evaluation workflow.

## Project Versions

- `Credit_Card_Fraud_Detection.ipynb` — initial version of the project
- `Credit_Card_Fraud_Detection_V2.ipynb` — improved version with stronger EDA, preprocessing, cross-validation, threshold tuning, and business interpretation
- `V3` — planned future improvement

## Overview

The goal of this project is to detect fraudulent credit card transactions using machine learning on a highly imbalanced real-world dataset.

Because fraud cases are rare, traditional accuracy is not sufficient for evaluating model performance. For this reason, the project focuses on imbalance-aware metrics such as precision, recall, F1-score, ROC-AUC, and PR-AUC.

## Business Problem

Credit card fraud detection is a high-impact classification problem. A useful model should not only identify fraud, but also balance two competing risks:

- missing fraudulent transactions
- generating too many false positive alerts

This makes fraud detection a strong example of why model evaluation must go beyond accuracy.

## Dataset

This project uses the **Credit Card Fraud Detection** dataset available on Kaggle.

### Dataset Characteristics
- **Rows:** 284,807 transactions
- **Columns:** 31 features
- **Target variable:** `Class`
  - `0` = Normal transaction
  - `1` = Fraudulent transaction

### Feature Information
- `Time` represents the time elapsed between each transaction and the first transaction in the dataset.
- `Amount` represents the transaction amount.
- `V1` to `V28` are anonymized PCA-transformed features.
- `Class` is the binary target variable.

### Why this dataset is challenging
The dataset is highly imbalanced:
- **Normal transactions:** 284,315
- **Fraudulent transactions:** 492

Fraud cases represent only a very small fraction of the data, which makes the problem significantly harder and requires evaluation beyond simple accuracy.

### Source Note
- The dataset is **not owned by me**.
- It is used here for **educational and portfolio purposes only**.
- Please refer to the original Kaggle dataset page for access and source details.

## Project Workflow

The V2 notebook follows a more structured machine learning workflow:

1. Problem framing  
2. Data loading and validation  
3. Dataset overview  
4. Exploratory data analysis  
5. Data preprocessing  
6. Baseline model: Logistic Regression  
7. Tree-based model: Random Forest  
8. Cross-validation and threshold tuning  
9. Model comparison  
10. Business interpretation  
11. Conclusion and next steps  

## Exploratory Data Analysis Highlights

The EDA stage was expanded in V2 to better understand the dataset before modeling.

Main focus areas:
- class imbalance
- transaction amount distribution
- log-transformed amount distribution
- hourly transaction behavior
- fraud rate by hour

### Sample EDA Visuals

**Class Distribution**  
_Add screenshot here_

**Log-Transformed Transaction Amount Distribution**  
_Add screenshot here_

**Fraud Rate by Hour**  
_Add screenshot here_

## Models and Evaluation

The project compares two main model families:

- **Logistic Regression** as a baseline model
- **Random Forest** as a tree-based non-linear model

Because this is a highly imbalanced classification problem, evaluation is based on:
- Precision
- Recall
- F1-score
- ROC-AUC
- PR-AUC

V2 also includes:
- **Stratified cross-validation**
- **Precision-recall curve analysis**
- **Threshold tuning** for Logistic Regression
- **Business-oriented interpretation** of false positives and false negatives

## Key Results

The final comparison includes three evaluated settings:

- Logistic Regression with default threshold (`0.5`)
- Logistic Regression with tuned threshold (`0.9`)
- Random Forest

### Final Results Summary

| Model | Precision | Recall | F1-Score | ROC-AUC | PR-AUC |
|------|-----------:|-------:|---------:|--------:|-------:|
| Logistic Regression (0.5) | 0.0559 | 0.9082 | 0.1054 | 0.9737 | 0.7222 |
| Logistic Regression (0.9) | 0.2037 | 0.8878 | 0.3314 | 0.9737 | 0.7222 |
| Random Forest | 0.9610 | 0.7551 | 0.8457 | 0.9622 | 0.8669 |

### Result Interpretation
- The default Logistic Regression model achieved very high recall, but produced too many false positive alerts.
- Threshold tuning improved Logistic Regression substantially by increasing precision and F1-score while keeping recall relatively high.
- Random Forest delivered the strongest overall fraud-class F1-score and the best precision-recall balance among the tested models.

### Metrics Snapshot
_Add screenshot of the final comparison table here_

## Business Interpretation

This project also evaluates results from an operational perspective.

### Missed Fraud vs False Alarms

| Model | False Positives | False Negatives | True Positives |
|------|----------------:|----------------:|---------------:|
| Logistic Regression (0.5) | 1502 | 9 | 89 |
| Logistic Regression (0.9) | 340 | 11 | 87 |
| Random Forest | 3 | 24 | 74 |

This comparison shows that:
- the default Logistic Regression model catches most fraud cases, but creates many false alarms
- threshold tuning reduces false positives substantially
- Random Forest produces very few false alarms, but misses more fraud than Logistic Regression

This highlights a central fraud detection trade-off: **minimizing missed fraud vs minimizing unnecessary alerts**.

## What's New in V2?

Compared with the initial notebook version, V2 includes:

- improved notebook structure and section flow
- clearer exploratory data analysis
- engineered `Hour` feature from transaction time
- cleaner preprocessing workflow
- cross-validation using PR-AUC
- threshold tuning for Logistic Regression
- Random Forest comparison
- final results comparison table
- business interpretation of false positives and false negatives
- improved readability and presentation

## Key Takeaways

This project showed that:

- imbalanced classification requires more than accuracy
- threshold choice can strongly affect practical performance
- model selection depends on business priorities
- reducing false alarms and minimizing missed fraud are competing objectives

## Repository Structure

- `Credit_Card_Fraud_Detection.ipynb` — initial notebook version
- `Credit_Card_Fraud_Detection_V2.ipynb` — improved notebook version
- `README.md` — project summary

## Limitations

- The dataset is highly imbalanced, which makes evaluation sensitive to a small number of fraud cases.
- Only a limited number of models were evaluated.
- The anonymized PCA-transformed features reduce interpretability.
- Threshold tuning was demonstrated on the test set, so a stricter validation strategy could strengthen the analysis further.

## Future Improvements

Possible next steps for V3:

- Random Forest cross-validation
- hyperparameter tuning
- additional imbalance-handling techniques such as SMOTE
- feature importance analysis
- stronger validation strategy for threshold selection
- improved visual summaries in the repository

## Note

This project is part of my learning journey while studying machine learning, including material from Andrew Ng’s Machine Learning course. The goal is to improve the project iteratively and build stronger practical understanding over time.
