# Enhancing App Rating & Install Prediction through Feature-Based Modeling
### Google Play Store Analysis

> Predicting mobile app success metrics using structured metadata and machine learning.

**Course:** Business Intelligence | **Date:** May 2025  
**Authors:** Rasheed Albel, Christian Paraan, Ada Plata

---

## Overview

With millions of apps competing on the Google Play Store, understanding what
drives **high ratings** and **large install counts** is critical for developers
and product teams. This project builds predictive models using app metadata
features — category, content rating, size, price, and review count — to forecast
both app ratings (regression) and install tier (classification).

---

## Objectives

- Identify which features most strongly predict app ratings and installs
- Build regression models for continuous rating prediction
- Build classification models for install count tier prediction
- Derive actionable insights for app developers

---

## Dataset

- **Source:** Google Play Store Apps Dataset (Kaggle)
- **Size:** ~10,000 apps with metadata
- **Target Variables:**
  - `Rating` — continuous (1.0–5.0 stars)
  - `Installs` — bucketed into tiers (e.g., 1K+, 10K+, 1M+)

### Key Features

| Feature        | Type        | Description                        |
|----------------|-------------|-------------------------------------|
| Category       | Categorical | App store category                 |
| Reviews        | Numerical   | Total user review count            |
| Size           | Numerical   | App size in MB                     |
| Price          | Numerical   | Free (0) or paid (>0)              |
| Content Rating | Categorical | Age appropriateness classification |
| Type           | Binary      | Free vs Paid                       |

---

## Methodology

### Data Preprocessing
- Handling missing values (Rating, Size, Content Rating)
- Parsing and cleaning `Installs` column (removing `+` and `,`)
- Encoding categorical variables (One-Hot / Label Encoding)
- Log-transforming skewed features (Reviews, Installs)
- Train/test split with stratification on install tier

### Models Explored

**For Rating Prediction (Regression):**
- Linear Regression (baseline)
- Random Forest Regressor
- Gradient Boosting Regressor

**For Install Prediction (Classification):**
- Logistic Regression (baseline)
- Random Forest Classifier
- Gradient Boosting Classifier

### Evaluation Metrics
- Regression: RMSE, MAE, R²
- Classification: Accuracy, Precision, Recall, F1, Confusion Matrix

---

## Key Findings

- **Review count** is the strongest predictor of both ratings and installs —
  apps with more social proof tend to perform better.
- **Free apps** dominate high-install tiers; price is a strong negative predictor
  of install count.
- **Category** significantly influences expected rating benchmarks
- Ensemble methods (Random Forest, Gradient Boosting) outperform linear baselines
  on both tasks.

---

## Feature Importance

Top features for install prediction (by importance score):
1. Reviews (log-scaled)
2. Type (Free/Paid)
3. Category
4. Size
5. Price

---

## Tech Stack

`Python` · `Pandas` · `NumPy` · `scikit-learn` · `Matplotlib` · `Seaborn`

---

## References 

- L. Gupta, "Google Play Store Apps," Feb 2019. [Online]. Available: https://www.kaggle.com/lava18/google-play-store-apps
---

## Acknowledgment of Tools

AI tools (e.g., ChatGPT) were used selectively to support code debugging and structure refinement; all analytical design, methodology selection, and interpretation were completed independently.

---

## Individual Contributions

This was a collaborative project completed as part of CSCI 113i: Business Intelligence.

My primary contributions included:
- Conducting exploratory data analysis (EDA) to identify key predictors of ratings and install tiers
- Implementing the Logistic Regression classification baseline for install-tier prediction
- Supporting feature preprocessing and transformation for structured metadata variables
- Performing model evaluation using accuracy, precision, recall, and F1-score metrics
- Preparing technical presentation slides summarizing methodology, results, and insights
