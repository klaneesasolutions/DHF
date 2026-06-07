# DHF
My DHF AI/ML ASSIGNMENTS
# Simple Linear Regression – Marketing ROI Analysis

## Project Overview
This project analyses a marketing dataset to determine which advertising channel (TV, Radio, or Social Media) has the greatest impact on sales. Using Python and `statsmodels`, I built a simple linear regression model, validated its assumptions, and translated the statistical findings into a clear ROI-based recommendation.

## Dataset
The dataset is the classic **Advertising** dataset (200 records) containing:
- **TV**: spend in thousands of dollars
- **Radio**: spend in thousands of dollars
- **Social_Media**: spend in thousands of dollars (originally 'Newspaper')
- **Sales**: product sales in thousands of units

Source: [An Introduction to Statistical Learning](https://www.statlearning.com/resources-python)

## Methodology
1. **Data cleaning & EDA**: Checked for missing values, visualised relationships with pairplots and correlation heatmaps.
2. **Variable selection**: Computed Pearson correlations; **TV** had the highest correlation with Sales (r ≈ 0.78).
3. **OLS regression**: Fitted `Sales ~ TV` using `statsmodels.formula.api.ols`.
4. **Diagnostic checks**: 
   - Residuals vs fitted (linearity)
   - Q-Q plot and Shapiro-Wilk test (normality)
   - Scale-location plot and Breusch-Pagan test (homoscedasticity)
5. **Interpretation**: Examined R², coefficient, and p-value to derive business insights.

## Key Findings
- **Model**: Sales = 7.03 + 0.0475 × TV  
- **R² = 0.612** → 61.2% of Sales variability explained by TV alone.
- **p-value < 0.001** → TV’s effect is statistically significant.
- Every additional $1,000 spent on TV advertising generates approximately **47.5 additional units sold**.

## Recommendation
**Allocate the largest portion of the marketing budget to TV advertising.**  
TV delivers the highest ROI per dollar spent among the three channels. The model provides a simple, interpretable tool for forecasting sales based on TV spend. Further analysis could incorporate interaction effects or non-linear relationships.

## Environment Setup
1. Clone this repository.
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels scipy
