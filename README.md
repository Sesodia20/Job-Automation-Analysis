# Job Automation Risk Analysis in the US Labour Market
Analysing US job automation risk and employment by combining Frey & Osborne automation scores with BLS projections, using clustering, regression, and ensemble methods.

## Overview

This project investigates which occupations face the highest risk of automation in the US
labour market, and what characteristics drive that risk, to support workforce-planning
decisions for businesses and policymakers.

It replicates and extends the Frey & Osborne automation framework by combining occupation-
level automation probabilities with official US Bureau of Labor Statistics (BLS) employment
projections, then applies clustering, regression, classification, and ensemble methods to
analyse and predict automation risk.

## Data

- **Automation probabilities by occupation** (Frey & Osborne framework), with state-level
  employment counts across all 50 US states and DC.
- **BLS 2024–2034 National Employment Matrix** — median wages, projected employment growth,
  and typical entry education by occupation.
- The two sources are merged on the shared SOC occupation code, yielding 607 matched
  occupations.

## Methods

- **Exploratory data analysis** — distributions, correlations, and risk patterns by
  education.
- **Clustering (K-Means)** — occupations grouped into four types by wage, growth, and
  employment size; automation risk deliberately excluded to avoid data leakage.
- **Regression (OLS)** — explaining automation risk, including an Education × Wage
  interaction and a VIF multicollinearity check.
- **Classification** — decision tree and logistic regression predicting high vs low risk.
- **Ensemble** — a voting classifier comparing hard and soft voting against the base models.

## Key Findings

- Automation risk is concentrated in lower-paid, lower-education, and declining occupations;
  higher-paid, higher-qualified, growing roles are largely protected.
- Education is the strongest single predictor of automation risk.
- The most intensely exposed roles are routine clerical and information-processing jobs;
  the most broadly exposed (by number of workers) are large-employment service and clerical
  occupations such as retail, cashiers, and office clerks.

## Repository Contents

- `Analysis.ipynb` — full analysis notebook (data integration through modelling).
- `data/` — datasets used in the analysis.

## Tools

Python (pandas, scikit-learn, statsmodels, matplotlib, seaborn), Jupyter Notebook.
