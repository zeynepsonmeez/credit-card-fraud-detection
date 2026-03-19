# Credit Card Fraud Detection

This project is part of my learning process while studying supervised machine learning.

The goal is to detect fraudulent credit card transactions using a real-world dataset with highly imbalanced classes.

## About the Dataset

The dataset contains transactions made by credit cards. Most of the transactions are normal, and only a very small portion are fraud cases.

This imbalance makes the problem more challenging and requires careful evaluation of models.

## What I Did

* Explored the dataset (EDA)
* Checked class distribution and imbalance
* Scaled the `Time` and `Amount` features
* Split the data using stratified sampling
* Trained two models:

  * Logistic Regression
  * Random Forest
* Evaluated models using:

  * Precision
  * Recall
  * F1-score
  * ROC-AUC
* Compared model performance

## Key Takeaways

* Accuracy is not a reliable metric for imbalanced datasets
* Logistic Regression achieved high recall but produced many false positives
* Random Forest provided a better balance between precision and recall
* Choosing the right metric depends on the problem (e.g. fraud detection vs false alarms)

## How to Run

1. Download the dataset (link or Kaggle reference)
2. Open the notebook
3. Run all cells

## Notes

This is one of my first machine learning projects. I focused on understanding the problem and comparing models rather than optimizing performance.

I plan to improve this project by adding:

* threshold tuning
* cross-validation
* more advanced models
