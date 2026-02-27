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
- Technical goal(s): Build an RI classifier that outperforms a logistic regression baseline on F1-score and PR-AUC while maintaining high Recall.
- Ethical considerations: Explicitly report the false-negative vs false-positive trade-off and include a disclaimer that the model is research-oriented and not for direct evacuation decisions.
- Sustainability considerations: Minimize computational footprint by selectively downloading and processing only relevant ERA5 variables and Atlantic-region subsets.

## Expected Results
We expect tree-based models (especially Random Forest) to provide stronger predictive performance than simpler baselines. We also expect physically meaningful predictors such as vertical wind shear, relative humidity, and sea surface temperature to emerge as highly important features, consistent with meteorological theory.

Potential limitations include class imbalance, temporal distribution shift across decades, and sensitivity to preprocessing/labeling choices.

---
[Back to Home]({{ '/' | relative_url }})
