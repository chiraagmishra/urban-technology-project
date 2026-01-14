# **German Migration Forecasting: Labor Market Predictors Study**

**Project Overview**

This repository contains a comprehensive analysis of the relationship between labor market conditions and foreign migration patterns across 16 German states from 2000-2024. The study employs global forecasting models, correlation analysis, and explainable AI techniques to test three key hypotheses about migration dynamics.

**Research Questions:**
1. Do job vacancies predict foreign migration patterns?
2. Does labor market tightness predict foreign migration patterns?
3. Can labor market indicators improve migration forecasts compared to baseline models?


**Methodology:**

Temporal Coverage: 2000-2024 (25 years)
Spatial Coverage: 16 German states (Bundesländer)
Target Variable: Foreign migration balance (migration_foreign)
Training Period: 2000-2019 (20 years)
Test Period: 2020-2024 (5 years, includes COVID-19 disruption)

**Models:**

Baseline Models (No Covariates):
1. Naive: Last observation carried forward
2. AutoARIMA: Automated ARIMA model selection

Global Models (With Labor Market Covariates):

3. Linear Regression
4. Random Forest
5. XGBoost
6. LightGBM

All global models trained simultaneously on 16 states, learning shared patterns while allowing state-specific predictions.

**Statistical Testing:**

Multiple Comparison Correction:

Bonferroni correction applied for state-level correlations
Original alpha: 0.05
Bonferroni-adjusted alpha: 0.003125 (0.05/16 states)
Controls family-wise error rate (FWER) at 5%

Hypothesis Tests:

H1 & H2: Pearson correlation per state, one-sample t-test on correlation distribution
H3: Paired t-test comparing baseline vs global model RMSE
Effect sizes: Cohen's d for all tests

**Explainability:**

SHAP (SHapley Additive exPlanations) values for feature importance
Global explanations aggregated across all states
Feature categorization: Labor market variables vs past migration patterns

## Limitations

### Data Constraints
- 25-year time series (limited for ML approaches)
- Annual aggregation misses within-year dynamics
- Test period contaminated by COVID-19 structural break

### Omitted Variables
- Housing costs and availability
- Wage levels and income inequality
- Education quality and university rankings
- Cultural amenities and quality of life indices
- Social networks and diaspora effects
- Immigration policy changes

## Future Research Directions

### Extended Analysis
- Higher frequency data (monthly/quarterly)
- Separate analysis by nationality groups
- State-specific (local) models for comparison
- Deep learning architectures (LSTM, Transformers)

### Additional Covariates
- Housing market indicators
- Regional GDP and economic growth
- Wage distributions and income inequality
- Education and research infrastructure
- Cultural diversity and integration measures
