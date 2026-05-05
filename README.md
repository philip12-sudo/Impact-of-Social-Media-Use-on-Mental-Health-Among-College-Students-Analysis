# Predicting the Impact of Social Media Use on Mental Health Among College Students

**Course:** GPH-GU 2338/3338 Machine Learning in Public Health, Spring 2026  
**Instructor:** Dr. Hai Shu  
**Authors:** Shuman Qi (sq2087), Boyuan Zhang (bz2118)  
**Group:** 20  

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![R Version](https://img.shields.io/badge/R-4.0+-blue.svg)

---

## Table of Contents

- [Overview](#overview)
- [Repository Contents](#repository-contents)
- [Data Source](#data-source)
- [Variables](#variables)
- [Requirements](#requirements)
- [How to Run the Analysis](#how-to-run-the-analysis)
- [Hyperparameter Tuning](#hyperparameter-tuning)
- [Key Results](#key-results)
- [Generalization (Overfitting Check)](#generalization-overfitting-check)
- [Feature Importance](#feature-importance)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [License](#license)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)
- [References](#references)

---

## Overview

This repository contains the code, data, and final report for our Machine Learning in Public Health final project. We used machine learning methods to predict the impact of social media use on mental health among college students.

We addressed two prediction tasks:
1. **Classification:** Predict whether a student's overall social media impact is Positive, Neutral, or Negative.
2. **Regression:** Predict a continuous mental health score (0-10).

The best-performing model was Random Forest, achieving a Macro F1 of 0.944 for classification and an RMSE of 0.528 (R² = 0.830) for regression. Daily usage hours and sleep quality were the dominant predictors, while demographic variables contributed minimally.

---

## Repository Contents

| File | Description |
|------|-------------|
| `Final_Project_Report_Group20.pdf` | The complete project report |
| `analysis.Rmd` | R Markdown script with all code (reproducible) |
| `analysis.pdf` | Knitted PDF output of the R Markdown script |
| `data/impact_of_social_media_on_health.csv` | The dataset used for analysis |
| `README.md` | This file |

---

## Data Source

The dataset is publicly available on Kaggle:

- **Title:** Impact of Social Media on Health
- **Author:** Sumeakash (2024)
- **Link:** https://www.kaggle.com/datasets/sumeakash/impact-of-social-media-on-health
- **Description:** 1,705 observations, 11 variables including demographic characteristics, social media usage patterns, and mental health outcomes.

The dataset is included in this repository. If you obtain it directly from Kaggle, ensure the file name matches.

---

## Variables

| Variable | Type | Role |
|----------|------|------|
| Age | Continuous | Predictor |
| Gender | Nominal | Predictor (one-hot encoded) |
| Academic Level | Ordinal | Predictor (label encoded) |
| Avg. Daily Usage Hours | Continuous | Predictor |
| Most Used Platform | Nominal | Predictor (one-hot encoded) |
| Affects Academic Performance | Binary | Predictor |
| Sleep Hours per Night | Continuous | Predictor |
| Distraction Level | Ordinal | Predictor (label encoded) |
| Academic Pressure | Ordinal | Predictor (label encoded) |
| Mental Health Score (0-10) | Continuous | Outcome (Regression) |
| Overall Impact (3-class) | Nominal | Outcome (Classification) |

The Country variable was excluded due to high cardinality (>30 levels).

---

## Requirements

To reproduce this analysis, you will need:

### R (if using R Markdown)
- R version 4.0 or higher
- Required packages:
  - `tidyverse` (data manipulation and visualization)
  - `caret` or `tidymodels` (model training and evaluation)
  - `randomForest` (Random Forest models)
  - `xgboost` (XGBoost models)
  - `ggplot2` (figures)
  - `corrplot` (correlation matrix visualization)
  - `nnet` (multinomial logistic regression)

Install all packages with:
```r
install.packages(c("tidyverse", "caret", "randomForest", "xgboost", "ggplot2", "corrplot", "nnet"))
