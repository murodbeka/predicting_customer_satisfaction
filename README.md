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


***X19 = -3.3626 + 0.2800X6 - 0.2352X7 + 0.3559X11 + 0.4496X12 + 0.2314X17 + 0.2446X20 + 0.2384*X21***


- **Positive impact**: Product Quality, Salesforce Image, Product Line, Price Flexibility, Likelihood to Recommend/Purchase
- **Negative impact**: E-Commerce (X7) — possibly due to lack of personal touch or technical issues

### 7. Recommendations

1. **Invest in Salesforce Image (X12)**  
   → Highest coefficient (0.45). Train sales teams, improve professionalism, and enhance client interactions.

2. **Improve Product Quality (X6)**  
   → Strong positive effect (0.28). Focus on consistency, durability, and innovation.

3. **Enhance Price Flexibility (X17)**  
   → Customers value negotiation and tailored pricing. Empower sales reps with discount authority.

4. **Leverage Advocacy (X20, X21)**  
   → Highly correlated with satisfaction. Encourage referrals and repeat purchases via loyalty programs.

5. **Re-evaluate E-Commerce (X7)**  
   → Negative coefficient. Audit the platform for usability, support, or integration issues.

6. **Monitor Delivery Speed (X18)**  
   → Dropped in final model but highly correlated. May need context-specific analysis.

---

## 📊 Visualizations Included
- Correlation heatmap
- Residuals vs. fitted values
- Q-Q plot for normality
- Histogram of residuals and satisfaction
- Pair plots of key variables

---

## 🚀 How to Run

1. Clone the repo:
   ```bash
   git clone https://github.com/yourusername/hbat-satisfaction-analysis.git
