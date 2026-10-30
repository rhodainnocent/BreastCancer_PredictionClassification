#  Breast Cancer Diagnostic Classification Prediction


## Project Overview
Early detection of breast cancer drastically improves patient prognosis and survival rates. This project implements an end-to-end Machine Learning pipeline to analyze medical diagnostic metrics derived from digitized Fine Needle Aspirate (FNA) images of breast masses. 

The primary objective is to accurately classify tumor samples as either Malignant (M) or Benign (B) while optimizing feature selection and model interpretability.

---

##  Key Technical Features & Workflow

- Exploratory Data Analysis (EDA): Analyzed feature distributions, missing values, duplicate records, and target class balance across 569 instances.
- Data Preprocessing & Cleaning: 
  - Redundant columns (id, Unnamed: 32) were removed.
  - Binary target encoding: **Benign (B) → 1 | Malignant (M) → 0**.
  - Stratified train-test split ($80/20$) to maintain class proportions.
- Feature Scaling & Selection: 
  - Applied MinMaxScaler for feature normalization.
  - Utilized univariate feature selection (SelectKBest with chi2) to isolate the top 8 most informative clinical features.
- Model Training & Evaluation: 
  - Trained a Logistic Regression classifier on the optimized feature set.
  - Generated full classification reports, precision, recall and F1-scores

---

## 📊 Dataset Summary

| Dataset Property | Value |
| :--- | :--- |
| Total Samples | 569 instances |
| Original Features | 30 numerical diagnostic features |
| Class Distribution | Benign: 357 (62.7%) \| Malignant: 212 (37.3%) |
| Selected Features | Top 8 statistically significant metrics |

### Top 8 Selected Features (via Chi-Squared Test):
1. concave points_mean
2. concave points_worst
3. concavity_mean
4. area_worst
5. perimeter_worst
6. radius_worst
7. concavity_worst
8. area_mean

---

## 📈 Model Performance

### Optimized Logistic Regression (8 Selected Features)
- Accuracy: 93.86%
- Demonstrates strong predictive capacity while drastically reducing model complexity and feature input requirements.

```text
              precision    recall  f1-score   support

Malignant (0)      0.95      0.88      0.91        42
   Benign (1)      0.93      0.97      0.95        72

    accuracy                           0.94       114
   macro avg       0.94      0.93      0.93       114
weighted avg       0.94      0.94      0.94       114
