# Engagement Lift Analysis — Steamly Recommender Experiment

## Overview

This project simulates and analyzes a product experiment for **Steamly**, a fictional media streaming platform. The goal is to evaluate the **causal impact of a new recommendation engine** on user engagement using principled modeling and diagnostic techniques.

Instead of a naive A/B comparison, this project demonstrates how **stratified regression, pre-trend validation**, and **propensity-adjusted estimation** can be used to approximate causal inference in observational settings.

## Objectives

- Simulate realistic engagement data for a feature rollout
- Detect and adjust for potential confounding via **propensity score modeling**
- Check for **pre-period trend imbalance** between groups
- Estimate average treatment effects using **linear models** and the **g-formula**
- Explore individual-level variation with **Mixed Effects Models**

---

## File Structure

| Notebook | Description |
|----------|-------------|
| `01_data_simulation.ipynb` | Simulates user-level engagement data across multiple periods and segments (e.g., cohort, user type, plan) |
| `02_exploratory_analysis.ipynb` | Explores engagement patterns and differences pre-/post-rollout |
| `03_pretrend_balance_checks.ipynb` | Validates baseline comparability via pre-period regression |
| `04_propensity_modeling.ipynb` | Builds a logistic regression model to estimate treatment propensity from pre-treatment covariates |

> Note: The focus is on demonstrating modeling logic and decision-making. Code is modular and streamlined for clarity over production-readiness.

---

## Methods Summary

- **Synthetic Data Simulation**: Creates longitudinal user data with known segment and time effects to reflect realistic product telemetry.
- **Pre-Trend Diagnostics**: Uses a fixed-effects regression to assess baseline trajectory alignment across treatment groups.
- **Propensity Score Modeling**: Estimates likelihood of treatment (exposure to new recommender) using user-level covariates (segment, plan, cohort).
- **Causal Estimation**: Applies regression with g-formula logic to estimate marginal treatment effects under covariate adjustment.
- **Heterogeneity Analysis**: Fits a random-intercept **Mixed Effects Model** on the pre-period to quantify variation in baseline engagement and ensure robustness of estimates.

---

## Key Takeaways

- The new recommender system shows a **positive and statistically significant impact** on engagement after adjustment.
- Pre-period modeling suggests **minimal imbalance**, supporting validity of the treatment effect estimate.
- Mixed-effects modeling captures user-level heterogeneity and strengthens causal interpretation by accounting for within-user correlation.

