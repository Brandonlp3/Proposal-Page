---
layout: default
title: Methods
---

# Methods

## Data Preprocessing Methods (3+)
1. Temporal alignment and merging of HURDAT2 track records with ERA5 atmospheric variables.
2. Atlantic-region filtering and selective variable extraction (for example, SST, wind shear, humidity, pressure).
3. Label construction for RI events using a 24-hour, 30-knot threshold.
4. Feature engineering on time-series observations (lags/windows) and normalization or scaling as needed.
5. Class imbalance handling for supervised learning (for example, class weights or resampling strategy).

## Machine Learning Algorithms / Models (3+)
1. K-Means clustering (unsupervised)
2. Gaussian Mixture Models (GMM) clustering (unsupervised)
3. Random Forest classifier (supervised)
4. Logistic Regression baseline (supervised benchmark)

## CS 7641 Coverage
- Supervised methods: Random Forest, Logistic Regression baseline
- Unsupervised methods: K-Means, Gaussian Mixture Models

## CS 4641 Coverage
- Supervised or Unsupervised methods used: Supervised and unsupervised methods are included via Random Forest/Logistic Regression and K-Means/GMM.

## Why These Methods
- K-Means provides an interpretable first pass at partitioning atmospheric storm states, with cluster count selected using elbow and silhouette analysis.
- GMM provides soft probabilistic assignments and flexible cluster shapes/sizes, reducing the risk that RI-prone minority patterns are absorbed by larger clusters.
- Random Forest is well-suited to high-dimensional meteorological predictors, supports feature importance analysis, and handles non-linear interactions.
- Logistic Regression provides a transparent baseline for comparison of discriminative performance.

Additionally, the supervised experiment design trains on older data (approximately 20-30 years ago) and evaluates on recent years to test both predictive generalization and the hypothesis of increasing RI frequency over time.

## Libraries / Packages
- scikit-learn: `KMeans`, `GaussianMixture`, `RandomForestClassifier`, `LogisticRegression`, and metrics utilities
- pandas / xarray: tabular and gridded time-series data preparation
- numpy: numerical preprocessing and feature construction

---
[Back to Home]({{ '/' | relative_url }})
