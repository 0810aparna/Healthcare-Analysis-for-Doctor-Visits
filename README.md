# Healthcare Analytics: Doctor Visit Analysis using Python

Exploratory data analysis of 5,190 respondents from the 1977-78 Australian Health Survey, looking at which factors are linked to how often people visit a doctor.

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, SciPy, Statsmodels, scikit-learn

## What the notebook covers
- Data quality checks (missing values, duplicates, data types, outliers), with each cleaning decision justified
- Feature engineering (age in years, income in AUD, insurance type, chronic-condition status)
- Univariate, bivariate and multivariate analysis (18 charts)
- Statistical tests: Mann-Whitney, Kruskal-Wallis, chi-square, bootstrap confidence intervals
- Count regression (Poisson to Negative Binomial) and logistic regression
- Insights, recommendations and limitations

## Key findings
- About 80% of people had no doctor visit in the 2-week window. The 93 people (1.8%) with 3 or more visits account for 27.8% of all visits.
- Illness count and days of reduced activity are the strongest predictors and stay significant after adjusting for other variables.
- Females visit more (about 1.24x after adjustment), but the gap fades from age 50 upward.
- Apparent effects of age, insurance type and income mostly shrink once health need is controlled for.
- 25% of rows are exact duplicates, but they are mostly healthy people with identical banded profiles (95% have zero visits), not data-entry repeats. They were kept, since dropping them would raise the mean visits from 0.30 to 0.39.

## Project structure
```
doctor-visit-analysis/
├── README.md
├── requirements.txt
├── Healthcare_Doctor_Visit_Analysis.ipynb
├── Healthcare_Doctor_Visit_Analysis.pdf
└── data/
    └── P2-Healthcare_Analytics_for_Doctor_Visits.csv
```

## How to run
```bash
git clone https://github.com/YOUR-USERNAME/doctor-visit-analysis.git
cd doctor-visit-analysis
pip install -r requirements.txt
jupyter lab
```
Open `Healthcare_Doctor_Visit_Analysis.ipynb` and choose Run All. In Google Colab, upload the notebook and run it; it will ask you to upload the CSV.

## Dataset
1977-78 Australian Health Survey, also published as `DoctorVisits` in the R package AER. Variable definitions: [AER DoctorVisits documentation](https://search.r-project.org/CRAN/refmans/AER/html/DoctorVisits.html).
`age` is stored as years/100 (band midpoints) and `income` in units of AUD 10,000 (top-coded). The notebook converts both.

## Limitations
- The data is from 1977-78 Australia and covers single adults only, with the young and old over-sampled. Results should not be generalised to today's population.
- Findings show association, not causation: illness and visits are measured in the same 2-week window.
- The logistic regression (AUC about 0.76) is in-sample only and was not tested on held-out data.
