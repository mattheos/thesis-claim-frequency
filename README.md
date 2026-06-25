# Thesis: A Comparative Study of Statistical Models and Machine Learning Methods for Insurance Claim Frequency Prediction

**Author:** Matthaios Iosif  
**Institution:** University of Groningen, Faculty of Science and Engineering  
**Programme:** Bachelor's Project Mathematics  
**Date:** June 2026  
**Supervisors:** Dr. W.P. Krijnen (first supervisor), Prof. M.A. Grzegorczyk (second assessor)

---

## Overview

This repository contains all R code used to fit, tune, and evaluate the models in the thesis. The analysis is applied to the freMTPL2freq French motor third-party liability dataset (677,991 policies) and compares seven modelling approaches for insurance claim frequency prediction: Poisson GLM, Negative Binomial GLM, Poisson GAM, GBM, XGBoost, GLMBoost, a two-stage Hybrid GLM+GBM, and a Super Learner ensemble. All models are evaluated on a held-out test set using Poisson deviance, RMSE, and lift curves.

---

## Repository Structure

| File | Description |
|------|-------------|
| `GLMs.Rmd` | Poisson and Negative Binomial GLM fitting and variable selection |
| `GAM.Rmd` | GAM covariate and basis function selection |
| `Boosting.Rmd` | GBM hyperparameter grid and cross-validation |
| `mboost.Rmd` | GLMBoost fitting across learning rates |
| `Hybrid.Rmd` | Two-stage Hybrid GLM+GBM model |
| `SuperLearner.nb.html` | Super Learner ensemble with custom exposure wrappers |
| `Final.Rmd` | Test-set evaluation, lift curves, calibration, and residual plots |

---

## Data

The analysis uses the `freMTPL2freq` dataset, available from the `CASdatasets` R package or from [Kaggle](https://www.kaggle.com). The dataset is not included in this repository. Place the CSV file in your working directory and update the file path at the top of each script accordingly.

---

## Dependencies

The following R packages are required:

```r
install.packages(c(
  "dplyr", "ggplot2", "caret", "gbm", "xgboost",
  "mboost", "mgcv", "MASS", "SuperLearner", "tidyr"
))
```

---

## Reproducibility

All scripts use `set.seed(123)` for the train/test split. Results may vary slightly across operating systems and package versions due to floating-point differences in gradient boosting implementations.
