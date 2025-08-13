# HBAT-200: Predicting Customer Satisfaction with Linear Regression

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-F37626)
![License](https://img.shields.io/badge/License-MIT-green)

This repository contains the analysis of the **HBAT-200 dataset** to identify key predictors of **customer satisfaction (X19)** using **linear regression**. The focus is on model development, diagnostics, interpretation, and actionable recommendations.

---

## 📌 Overview

Customer satisfaction is a key performance indicator in competitive markets. Using the HBAT-200 dataset, this project:

- Builds a **linear regression model** using only **numerical predictors**.
- Excludes categorical/binary variables (e.g., `X1`, `X2`, `X4`) to ensure model clarity.
- Applies **feature selection** (stepwise and backward) to refine the model.
- Validates **regression assumptions**.
- Delivers **interpretable results** and **strategic recommendations**.

---

## 📂 Files

- `HBAT_analysis.ipynb` – Jupyter notebook with full analysis.
- `HBAT-200-Data.csv` – Dataset (not included; available upon request or via standard sources).
- `README.md` – This file.

---

## 🔍 Key Steps

### 1. Initial Model Summary
- Ran OLS regression with all numerical predictors.
- Found high R² (0.882), but many insignificant variables and multicollinearity.

### 2. Model Selection
- **Stepwise selection** and **backward elimination** used to identify significant predictors.
- Final model includes: `X6, X7, X11, X12, X17, X20, X21`

### 3. Final Model Summary
- **R² = 0.846**, **Adjusted R² = 0.840**
- **F-statistic = 131.5 (p < 0.001)** → Model is highly significant
- All predictors significant at **p < 0.05** (except minor edge on X7)
- **Lower AIC/BIC** than full model → better fit, less overfitting
- **Condition Number = 607** → moderate multicollinearity (improved from 1360)

### 4. Assumption Checks
- ✅ **Normality**: Shapiro-Wilk (p = 0.212) → residuals are normal
- ❌ **Homoscedasticity**: Breusch-Pagan test (p < 0.05) → heteroscedasticity detected
- ✅ **Linearity**: Residuals vs. fitted plot shows no clear pattern
- ⚠️ **Multicollinearity**: VIF values < 5 for all → acceptable

### 5. Correlation Analysis
- Heatmap shows strong positive correlations between satisfaction and:
  - `X20` Likely to Recommend
  - `X21` Likely to Purchase
  - `X12` Salesforce Image
  - `X6` Product Quality

### 6. Interpretation
**Final Prediction Equation:**
