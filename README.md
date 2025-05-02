![](UTA-DataScience-Logo.png)

# Customer Churn Prediction Project

## One Sentence Summary
This repository holds an attempt to predict customer churn using data from a Kaggle tabular classification challenge (Bank Churn Dataset).

## Overview
The task was to predict whether a bank customer would exit the bank based on features such as credit score, age, tenure, balance, and others. We approached this as a binary classification problem using Random Forest and Logistic Regression classifiers to model customer behavior. The data was preprocessed by cleaning, applying one-hot encoding to categorical features, and standardizing numerical features. Among the models tested, Random Forest performed best, achieving over 86% accuracy with a good balance between precision and recall.
---

## Summary of Work Done

### Data
- **Type**: Tabular CSV file
- **Input**: Customer demographic and banking activity features
- **Output**: Churn flag (Exited: 0 = Stayed, 1 = Left)
- **Size**: 
  - Train: ~80%
  - Test: ~20%

### Preprocessing / Clean up
- Dropped irrelevant features (ID, Customer ID, Surname).
- One-hot encoded categorical features (`Geography`, `Gender`).
- Standardized numerical features (`Age`, `CreditScore`, etc.) using `StandardScaler`.

### Data Visualization
- Normalized histograms of features like `Age`, `CreditScore`, etc. split by exited/stayed customers.
- Bar charts for categorical features.
- Identified features like `Age` and `CreditScore` as strongly correlated to churn.
#### Some Feature Visualizations

![](HistAge.png)
![](HistCreditScore.png)
![](HistGeo.png)
![](HistGender.png)
---

## Problem Formulation

- **Input**: Customer features after preprocessing.
- **Output**: Binary classification (Exited: 0 or 1).

### Models
- **Random Forest Classifier**
- **Logistic Regression**

Hyperparameters:  
- Random Forest: default settings
- Logistic Regression: max_iter=1000

---

## Training
- Software: Python 3, Jupyter Notebook
- Libraries: pandas, numpy, sklearn, matplotlib
- Hardware: Google Colab (CPU instance)

Training took about 5–10 minutes total.

---

## Performance Comparison

| Model                 | Accuracy | Precision | Recall | F1 Score |
|:----------------------|:---------|:----------|:-------|:---------|
| Random Forest          | 0.865    | 0.790     | 0.500  | 0.610    |
| Logistic Regression    | 0.840    | 0.740     | 0.450  | 0.560    |

- **ROC curves** were plotted for model evaluation.
- **Random Forest** performed better across most metrics.

---

## Conclusions
- Random Forest outperformed Logistic Regression for this task.
- Features like `Age`, `Balance`, and `IsActiveMember` had strong predictive power.

---

## Future Work
- Try boosting algorithms like **XGBoost** or **LightGBM**.
- Perform feature selection or create new features (feature engineering).
- Hyperparameter tuning (e.g., using GridSearchCV).

---

## How to Reproduce Results

1. Clone this repository.
2. Open `KaggleChallenge.ipynb` notebook.
3. Install requirements (`pip install -r requirements.txt` if necessary).
4. Run all cells in order.
5. `submission.csv` will be created for Kaggle submission.

---

## Overview of Files in Repository

| File | Description |
|:-----|:------------|
| `KaggleChallenge.ipynb` | Main notebook for model training and evaluation |
| `submission.csv` | Final prediction file for Kaggle submission |
| `train.csv` | Training dataset |
| `test.csv` | Test dataset |

---

## Citation

> Reade, W., & Chow, A. (2024). *Binary Classification with a Bank Churn Dataset*. Kaggle.  
> https://kaggle.com/competitions/playground-series-s4e1

## Software Setup

- Python 3
- pandas
- numpy
- scikit-learn
- matplotlib

Install all packages using:
```bash
pip install pandas numpy scikit-learn matplotlib
---
