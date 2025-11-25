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

  
