---
layout: default
title: Potential Results and Discussion
---

# Results and Discussion

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


---
[Back to Home]({{ '/' | relative_url }})
