# Healthcare-Analysis-for-Doctor-Visits
Exploratory data analysis of 5,190 respondents from the 1977-78 Australian Health Survey, covering what drives doctor visits. Python (Pandas, NumPy, Matplotlib, Seaborn, SciPy, Statsmodels), with Negative Binomial and logistic regression.
This notebook runs an end-to-end exploratory data analysis on a doctor-visit survey dataset (5,190 people, 12 variables, from the 1977-78 Australian Health Survey) to find out which factors are linked to how often people see a doctor.

What it covers

Data quality checks (missing values, duplicates, types, outliers), with each cleaning decision justified
Feature engineering (age in years, income in AUD, insurance type, chronic-condition status)
Univariate, bivariate and multivariate analysis with 18 charts
Statistical testing: Mann-Whitney, Kruskal-Wallis, chi-square and bootstrap confidence intervals
Count regression (Poisson to Negative Binomial) and logistic regression, with insights, recommendations and limitations

Key findings

About 80% of people had no visit in the 2-week window. The 1.8% with 3 or more visits account for 27.8% of all visits.
Illness count and days of reduced activity are the strongest predictors, and they stay significant after adjusting for the other variables.
Females visit more (about 1.24x after adjustment).
Apparent effects of age, insurance and income mostly shrink once health need is controlled for.
25% of rows are exact duplicates but represent genuinely identical banded profiles, not data-entry repeats, so they were kept.

Limitations: the data is from 1977-78 Australia, covers single adults only, and shows association rather than causation.

Tools: Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, Statsmodels, scikit-learn
