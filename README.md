# water-quality-risk-analysis
**Machine Learning Classification + Risk Scoring + Power BI Dashboard**

This project predicts water potability (safe vs unsafe for drinking) using machine learning and generates a Risk Score for each sample. It also includes an interactive Power BI dashboard to help water authorities and researchers monitor contamination risks.

Dataset sourced from Kaggle – Water Quality Dataset.

# Project Overview

Safe drinking water is essential for public health. This project develops a data-driven risk intelligence system that:

- Predicts whether a water sample is safe (1) or unsafe (0)
- Generates a Risk Score (0–1) reflecting the probability of water being safe
- Provides an interpretable ML model (Random Forest)
- Builds an interactive Power BI dashboard for monitoring quality indicators

The solution can help municipal bodies, NGOs, and policy institutions like CEEW assess water safety at scale.

| Variable        | Description                        |
| --------------- | ---------------------------------- |
| pH              | Water acidity/alkalinity           |
| Hardness        | Calcium & magnesium concentration  |
| Solids (TDS)    | Total dissolved solids (mg/L)      |
| Chloramines     | Chloramine level in mg/L           |
| Sulfate         | Sulfate concentration              |
| Conductivity    | Conductance of water               |
| Organic_carbon  | Organic carbon concentration       |
| Trihalomethanes | THMs — toxic compounds             |
| Turbidity       | Clarity of water                   |
| Potability      | Target label: 1 = safe, 0 = unsafe |


# Data Cleaning & Preparation

- Handled missing values using median imputation
- Created engineered features:
- High_turbidity
- low_ph
- High_solids
- Normalized continuous variables
- Encoded target variable:
1 = Safe (Potable)
0 = Unsafe (Not Potable)

# Exploratory Data Analysis

Key observations:

- Safe samples (1) were less frequent than unsafe samples.

- Lower pH and higher turbidity strongly correlated with unsafe water.

- Conductivity and sulfate levels varied widely across samples.

- Risk Score distributions showed clear separation between classes

# Model Performance Summary

Three classification models were evaluated to predict water potability (1 = Safe, 0 = Unsafe).
Because the dataset is imbalanced, precision, recall, and F1-score are more informative than accuracy.

| **Model**               | **Accuracy** | **Precision (Class 0)** | **Recall (Class 0)** | **Precision (Class 1)** | **Recall (Class 1)** | **Key Insight**                                         |
| ----------------------- | ------------ | ----------------------- | -------------------- | ----------------------- | -------------------- | ------------------------------------------------------- |
| **Logistic Regression** | 0.61         | 0.61                    | 1.00                 | 0.00                    | 0.00                 | Predicts everything as *Not Potable* → Not useful       |
| **Random Forest**       | **0.66**     | 0.66                    | **0.90**             | 0.64                    | 0.29                 |  **Best model** — Excellent at detecting unsafe water |
| **XGBoost**             | 0.65         | **0.67**                | 0.84                 | 0.59                    | **0.36**             | Balanced model; slightly weaker than RF                 |

# Risk Score Generation

After training, the best model produces:

Risk_Score = Probability that the water sample is SAFE


Values closer to 1.0 → High confidence the sample is safe

Values closer to 0.0 → High risk / unsafe water


# Power BI Dashboard

The Power BI dashboard includes:

✔ Key KPIs

Total Samples

Total Safe

Total Unsafe

Average Risk Score

✔ Visuals

Donut Chart — Potability Distribution

Bar Chart — Average Risk Score by Potability

Histogram — Risk Score Distribution

Scatterplots:

Turbidity vs Risk Score

pH vs Risk Score

Solids vs Risk Score

✔ Slicers

Potability

Risk Category (Low | Medium | High)

![Water Quality Risk Dashboard](https://github.com/SaurabhKumar-Singh/water-quality-risk-analysis/blob/main/water-quality-risk%E2%80%90analysis/Dashboard_Pic.JPG?raw=true)
