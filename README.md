# Credit Card Fraud Detection (XGBoost)

This project builds an end-to-end machine learning pipeline to predict fraudulent credit card transactions.
The focus is on handling an imbalanced classification problem and making practical decisions around evaluation metrics and probability thresholds.

Rather than maximising accuracy, the project emphasises fraud recall, false-positive trade-offs, and interpretability.

---

## Business context

Credit card fraud is a high-risk, low-frequency problem.  
Missing fraud is costly, but overly aggressive models can block legitimate customers and damage user experience.

The goal of this project is to:
- predict the probability of fraud for each transaction
- evaluate performance using metrics suitable for imbalanced data
- explore decision thresholds that balance fraud detection against false positives

---

## What the notebook covers

- Loading and cleaning a raw Excel dataset containing metadata rows
- Exploratory data analysis and correlation inspection
- Training an XGBoost classifier for fraud prediction
- Handling class imbalance using appropriate evaluation metrics
- Model evaluation using ROC-AUC, PR-AUC, and confusion matrices
- Threshold analysis to understand recall vs false-positive trade-offs
- Feature importance inspection to sanity-check model behaviour
- Batch prediction on recent transactions with CSV export

---

## Tech stack

- Python  
- pandas, numpy  
- scikit-learn  
- XGBoost  
- matplotlib, seaborn  

---

## Repository structure

