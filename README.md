# 🧬 Gene-Environment Interaction Regression Analysis

By Arjun Talapatra

This project applies multiple regression techniques to evaluate the impact of **genetic (G)** and **environmental (E)** variables on an outcome variable **Y**. The analysis examines both **main effects and interactions**, applies model transformations, and uses statistical selection techniques to build the best predictive model.

---

## 🎯 Objectives

- Determine whether genetic variables (G1–G20) are associated with outcome **Y** after controlling for environmental variables (E1–E4)
- Investigate gene-gene (G×G) and gene-environment (G×E) interaction effects
- Apply model diagnostics, Box-Cox transformation, and stepwise regression
- Use statistical tests and model criteria to justify the final regression model

---

## 🧰 Tools & Technologies

- 💻 **R** and **RStudio**
- 📦 `MASS`, `leaps`, `knitr`
- 🔢 Linear regression, interaction modeling, Box-Cox transformation
- 📊 Model selection using Adjusted R², BIC, and p-values

---

## 📂 Files Included

| File | Description |
|------|-------------|
| `P2_602237.csv` | Raw dataset with environmental and genetic variables |
| `gene_environment_analysis.R` | All R code used in the project |
| `Project_Report.pdf` | Full write-up with tables, code, model output, and interpretation |

---

## 🧪 Methodology Summary

1. **Model 1 – Environmental Only**  
   Fit a base linear model using only E1–E4.

2. **Model 2 – Full G + E with Interactions**  
   Include all genetic variables and second-order interaction terms (G×G, G×E, E×E).

3. **Residual Analysis & Transformation**  
   Performed Box-Cox transformation → chose λ = 0.5 → modelled √Y.

4. **Model Selection**  
   Used `regsubsets()` for forward stepwise regression (5 best models).  
   Selected final model based on BIC and Adjusted R².

5. **Final Model Variables**  
   - **G17**
   - **E2**
   - **E4**
   - **G5 × E4** (interaction)

6. **Multiple Comparisons**  
   Applied **Bonferroni correction** to control Type I error across multiple hypothesis tests.

---

## 📊 Key Results

- 📌 **Final Model**:  
  √Y = β₀ + β₁·G17 + β₂·E2 + β₃·E4 + β₄·(E4 × G5) + ε

- ✅ All model terms significant at α = 0.05  
- 📈 Adjusted R² = 0.51 after Box-Cox transformation  
- 📉 Residuals appear normal and homoscedastic post-transformation  
- ❌ No significant G×G interactions found  
- ✔️ Only one G×E interaction significant: **G5 × E4**

---

## 📈 Statistical Techniques Demonstrated

- Multiple linear regression with up to second-order interactions
- Residual plots & diagnostic evaluation
- Box-Cox transformation (`boxcox()` from `MASS`)
- Stepwise regression model selection (`regsubsets()` from `leaps`)
- Significance testing (t-test, p-values)
- Bonferroni correction for multiple comparisons

---

## 📝 Report

https://github.com/atalapatra72-bit/Multiple-Regression-Computing/blob/main/Multiple%20Regression%20Computing%20Project.pdf

---
