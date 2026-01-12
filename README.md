# Credit Card Fraud Detection (XGBoost)

This project builds an end-to-end machine learning pipeline to predict fraudulent credit card transactions.
The focus is on handling an imbalanced classification problem and making practical decisions around evaluation metrics and probability thresholds, rather than maximising accuracy alone.

---

## Business context

Credit card fraud is a high-risk, low-frequency problem.
Missing fraud is costly, but overly aggressive models can block legitimate customers and degrade user experience.

The goal of this project is to predict transaction-level fraud probabilities and explore decision thresholds that balance fraud detection against false positives.

---

## Dataset
- 1,000,000 credit card transactions
- Severe class imbalance: X% fraud rate (typical of real-world fraud detection)
- Features include transaction amount, location data, merchant category, timestamp, etc.

---

## Technical approach
- **Imbalanced data**: Applied class weighting in XGBoost to penalize misclassification of rare fraud cases
- **Evaluation strategy**: Prioritized PR-AUC over ROC-AUC due to severe class imbalance (better reflects performance on minority class)
- **Threshold tuning**: Analyzed recall vs precision at multiple thresholds to understand operational trade-offs

---
  
## Key outcomes

- Trained an XGBoost-based fraud detection model achieving a **ROC-AUC of 1.00** and **PR-AUC of 0.9997**, indicating strong separation between fraudulent and non-fraudulent transactions on an imbalanced dataset
- At a probability threshold of **0.50**, the model achieved a fraud recall of approximately **99.1%**, missing only a small fraction of fraudulent transactions
- At this threshold, around **8.8%** of total transactions were flagged for review, illustrating the trade-off between fraud capture and operational volume
- Feature importance analysis showed that transaction behaviour and location-based features were among the strongest drivers of fraud predictions, aligning with expected fraud patterns
- Generated batch predictions for the most recent **5,000 transactions**, exporting fraud probabilities and binary predictions for downstream analysis

---

## What the notebook covers

- Loading and cleaning a raw Excel dataset containing metadata rows
- Exploratory data analysis and correlation inspection
- Training an XGBoost classifier for fraud prediction
- Evaluation using ROC-AUC, PR-AUC, confusion matrices, and classification reports
- Threshold analysis to understand recall vs false-positive trade-offs
- Feature importance inspection to sanity-check model behaviour
- Batch prediction and CSV export of fraud results

---

## Tech stack

- Python  
- pandas, numpy  
- scikit-learn  
- XGBoost  
- matplotlib, seaborn

Note: The near-perfect ROC-AUC reflects strong feature engineering and relatively clean separation in this dataset. In production scenarios with noisier data and evolving fraud patterns, continuous monitoring and retraining would be essential.

---

## Repository structure

