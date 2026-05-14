# 🏦 Credit Risk Analysis — Data Mining Pipeline

A full data mining pipeline applied to a real-world credit risk dataset (25,418 records). The project combines unsupervised clustering, fuzzy logic reasoning, and genetic optimization to build an automated loan screening system.

---

## 📁 Dataset

| Dataset | Records | Task |
|---|---|---|
| **Credit Risk Dataset** | 25,418 (after preprocessing) | Clustering & Risk Classification |

**Key Predictors Identified:**
- `loan_percent_income` — strongest default predictor (r = 0.37)
- `loan_int_rate` — second strongest (r = 0.34)

---

## 🧪 Methods Implemented

### 📊 Exploratory Data Analysis (EDA)
- Correlation analysis to identify default predictors
- Distribution profiling across all features

### 🔧 Preprocessing
- Outlier removal via IQR
- Missing value imputation (median-based for interest rate)
- `sqrt` transformation on `person_age`
- Feature encoding & scaling

### 🔵 K-Medoids Clustering
- K = 2 clusters
- Higher-risk group: 20.9% default rate (higher interest + loan burden)
- Lower-risk group: 19.1% default rate
- **Silhouette Score: 0.1422**

### 🌿 Hierarchical Clustering
- Complete linkage, K = 2
- Clearer separation: 35.7% vs 11.6% default rate
- Confirms the same two risk profiles
- **Silhouette Score: 0.1464**

### 🌀 Fuzzy Logic System
- Inputs: interest rate, loan-to-income ratio, cluster label
- 13 fuzzy rules → risk score (0–100) via centroid defuzzification
- Output: **Approve / Review / Reject**
- **Validation Accuracy: 81/97 (83.5%)**

### 🧬 Genetic Algorithm
- **Feature Selection** — maximizing Random Forest accuracy
- **Fuzzy MF Tuning** — replacing manual thresholds with data-driven boundaries

---

## 📊 Results Summary

| Method | Metric | Score |
|---|---|---|
| **K-Medoids** | Silhouette Score | 0.1422 |
| **Hierarchical Clustering** | Silhouette Score | 0.1464 |
| **Fuzzy Logic System** | Validation Accuracy | 83.5% (81/97) |

> Silhouette scores of ~0.14 are acceptable for financial data, where natural cluster separation is rarely sharp due to overlapping risk profiles.

---

## 💼 Business Value

> The pipeline enables lenders to **automate loan screening** — approving low-risk applicants instantly, rejecting high-risk ones, and routing borderline cases to human review — replacing manual assessment with a data-driven, interpretable system.

**Sample GA Output:**
```
Decision : Reject
Score    : 66.22
Cluster  : 0
```

---

## 🗂️ Project Structure

```
├── data/
│   └── credit_risk_dataset
├── notebook/
│   └── DM_Project.ipynb
└── README.md
```

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![scikit-learn](https://img.shields.io/badge/scikit--learn-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualization-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebooks-orange?logo=jupyter)

