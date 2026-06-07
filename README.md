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
R²	0.999	TV spend explains 99.9% of variance in Sales
Adj. R²	0.999	Confirms no over-fitting with single predictor
Intercept (β₀)	-0.1325	Negligible; p=0.188 (not statistically significant)
TV Coefficient (β₁)	3.5615	Every 
3,561.50 in Sales**
p-value (TV)	< 0.0001	Highly significant — reject H₀
F-statistic	4,517,000	Model is globally significant
Durbin-Watson	1.998	~2.0 → no serial autocorrelation
Jarque-Bera p	0.985	Residuals are normally distributed ✓

## Recommendation
TV is the highest-confidence marketing investment. While its per-dollar return (
1) is lower than Radio or Social Media in isolation, it provides near-perfect predictability (R²=0.999), 
allowing reliable sales forecasting and budget planning. A 
178,075 in incremental sales.

Strategic Budget Allocation Suggestion:

Primary channel: TV (60–70% of budget) — highest reliability for revenue forecasting
Secondary: Radio (20–25%) — strong correlation, decent ROI
Experimental: Social Media (10–15%) — high raw coefficient but noisy; test and measure carefully

## Environment Setup
1. Clone this repository.
2. Install dependencies:
   ```bash
   pip install pandas numpy matplotlib seaborn statsmodels scipy
