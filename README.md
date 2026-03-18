# Credit Card Fraud Detection

## About the Project
In this project, I worked on detecting fraudulent credit card transactions using machine learning.

This is my first end-to-end machine learning project where I went through the full process from data analysis to model evaluation.

---

## Dataset
The dataset comes from Kaggle and contains anonymized credit card transactions.

It is highly imbalanced, meaning fraud cases are very rare compared to normal transactions.

(The dataset is not included due to its size.)

---

## What I Did
- Explored the dataset (EDA)
- Checked class imbalance
- Scaled features (Time, Amount)
- Split data into train and test sets
- Built classification models
- Compared model performance

---

## Models
- Logistic Regression
- Random Forest

---

## Results
Logistic Regression:
- Very high recall
- Very low precision
- Catches most fraud cases but gives many false alarms

Random Forest:
- High precision
- Lower recall
- Fewer false alarms but misses some fraud cases

---

## Key Takeaway
There is a trade-off between precision and recall in fraud detection.

Depending on the goal:
- Use Logistic Regression to catch more fraud
- Use Random Forest to reduce false positives

---

## Tools Used
- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn

---

## Next Steps
- Try SMOTE
- Test more models (XGBoost)
- Improve model tuning
