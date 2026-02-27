---
layout: default
title: Potential Results and Discussion
---

# (Potential) Results and Discussion

## Quantitative Metrics (3+)
1. Recall
2. Precision
3. F1-score
4. PR-AUC

## Project Goals
The performance of the RI classifier will be evaluated using
robust metrics to class imbalance: Recall, Precision, F1-score,
and PR-AUC. The primary goal is to outperform logistic
regression in F1-score and PR-AUC while maintaining high
Recall to minimize RI events.
Regarding sustainability, we will minimize our computa-
tional footprint by selectively downloading ERA5 variables
and regions. Ethically, we will explicitly report the trade-
off between false negatives and false positives, including a
disclaimer that this research-oriented model is not intended
for direct real-world evacuation decisions. We expect tree-
based models, such as Random Forest, to demonstrate superior
predictive power. Furthermore, we anticipate that physically
significant features-including wind shear, relative humidity,
and sea surface temperature-will emerge as the top predictors,
aligning with established meteorological theory.

HURDAT2 timestamp and storm location (e.g., using the
nearest ERA5 grid point or bilinear interpolation), so that each
6-hour storm observation has a matched set of environmental
features. When appropriate, we optionally summarize the
local environment by averaging ERA5 variables over a small
neighborhood around the storm center to reduce sensitivity to
single-grid-cell noise.
We then clean the data by flagging invalid entries and
imputing missing values (within-storm time-neighbor fill when
possible, otherwise training-set medians). We build a compact
feature set (storm state plus recent 6–12h changes and trans-
lation speed) and standardize continuous predictors for scale-
sensitive models.

## Expected Results
We expect tree-based models (especially Random Forest) to provide stronger predictive performance than simpler baselines. We also expect physically meaningful predictors such as vertical wind shear, relative humidity, and sea surface temperature to emerge as highly important features, consistent with meteorological theory.

Potential limitations include class imbalance, temporal distribution shift across decades, and sensitivity to preprocessing/labeling choices.

---
[Back to Home]({{ '/' | relative_url }})
