# Simple Linear Regression – Marketing ROI Analysis

## Project Overview
This project applies simple linear regression to a marketing dataset to identify which advertising channel (TV, Radio, or Social Media) most effectively drives Sales. Using Python and `statsmodels`, I performed exploratory data analysis, selected the strongest predictor, built and validated an OLS regression model, and translated the statistical outputs into a clear budget allocation recommendation.

## Dataset
- **Source**: `marketing_and_sales_data_evaluate_lr.csv`
- **Records**: 4,572 observations (4,546 after cleaning)
- **Features**:  
  - `TV` – TV advertising spend (thousands of dollars)  
  - `Radio` – Radio advertising spend (thousands of dollars)  
  - `Social_Media` – Social Media advertising spend (thousands of dollars)  
  - `Sales` – Product sales (thousands of units)

Missing values were minimal (<0.3% per column) and were handled via listwise deletion.

## Methodology
1. **Data Cleaning**: Checked for missing values; dropped rows with any `NaN` (26 rows removed, final N = 4,546).
2. **Exploratory Data Analysis (EDA)**:
   - Distribution plots and pairplots to inspect linearity and outliers.
   - Correlation heatmap to quantify relationships.
3. **Variable Selection**: Pearson correlation with Sales ranked:
   - TV: r = 0.9995 (≈99.9% of variance explained)
   - Radio: r = 0.8686
   - Social_Media: r = 0.5274  
   **TV** was selected as the single independent variable due to its near-perfect linear relationship.
4. **OLS Regression Model**:  
   Model: `Sales = β₀ + β₁ × TV + ε`  
   Fitted using `statsmodels.OLS`.
5. **Assumption Diagnostics**:
   - **Linearity**: Residuals vs. fitted values show random scatter.
   - **Normality**: Q‑Q plot aligns closely with the diagonal; Jarque‑Bera test p = 0.985 (fail to reject normality).
   - **Homoscedasticity**: Scale‑location plot confirms constant variance.
   - **Independence**: Durbin‑Watson statistic = 1.998 ≈ 2.0.
6. **Interpretation & ROI Recommendation**: Translated coefficients and R² into actionable marketing budget advice.

## Key Results
- **Regression Equation**:  
  `Sales = -0.1325 + 3.5615 × TV`
- **R²** = 0.999 → TV spend alone explains **99.9%** of the variation in Sales.
- **TV Coefficient** = 3.5615 (p < 0.0001) → Every additional $1,000 spent on TV advertising yields approximately **$3,561.50 in incremental sales**.
- **Intercept** (const = -0.1325, p = 0.188) is not statistically significant, confirming the relationship passes through near the origin.

## ROI Comparison & Business Recommendation

| Channel      | Coefficient (Sales per $1K) | R²    | Reliability    |
|--------------|-----------------------------|-------|----------------|
| TV           | $3,561.50                   | 0.999 | ★★★★★ Highest |
| Radio        | $8,360 (approx.)*           | 0.754 | ★★★☆☆ Moderate|
| Social Media | $22,190 (approx.)*          | 0.278 | ★☆☆☆☆ Low     |

*Radio and Social Media coefficients were obtained from separate simple regressions; their R² values indicate lower predictive reliability.*

**Recommendation**:  
Allocate **60–70% of the marketing budget to TV advertising**. TV offers near‑perfect predictability (R² = 0.999), making it a reliable engine for sales forecasting and revenue planning. Radio (20–25%) can be used as a secondary channel to capture additional returns with moderate confidence. Social Media (10–15%) shows a high raw coefficient but explains only 27.8% of the variation; it should be treated as an experimental channel, with results carefully tracked before scaling.

## Environment Setup
1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <repo-folder>
Install required Python packages:

bash
pip install pandas numpy matplotlib seaborn statsmodels scipy
Place the dataset marketing_and_sales_data_evaluate_lr.csv in the root directory.

Launch Jupyter Notebook:

bash
jupyter notebook regression_analysis.ipynb
Run all cells to reproduce the analysis.

Repository Structure
regression_analysis.ipynb – Full analysis notebook with code, visualisations, and explanations.

README.md – Project overview and findings.

marketing_and_sales_data_evaluate_lr.csv – Dataset (add to .gitignore if large or confidential).

Author
Kassim Busari
