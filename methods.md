---
layout: default
title: Methods
---

# Methods
A. Data Preprocessing Methods
We begin with the provided HURDAT2 (6-hour) storm-track
records and the accompanying ERA5 atmospheric variables.
Our preprocessing focuses on making these sources consistent
and model-ready. First, we align ERA5 predictors to each
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


## CS 7641 Coverage
- Supervised methods: Random Forest, Logistic Regression baseline
- Unsupervised methods: K-Means, Gaussian Mixture Models


## Supervised
The supervised learning portion of this project will involve
building a model to predict if a storm will experience rapid
intensification within a designated time period in the future
(for example, within 24 hours). The model will be a binary
classifier, determining whether or not rapid intensification will
occur.

Alongside building a classifier, one of the project’s hypothe-
ses is that rapid intensification is occurring more frequently
now compared to 20-30 years ago. Therefore, this binary
classifier will be trained on data from 20-30 years ago,
and tested against more recent data. This separation of the
dataset will provide dual use: testing the accuracy of our
binary classifier, and testing our hypothesis that storms more
frequently experience rapid intensification.

A potential candidate for the binary classifier model is
random forest. This model is ideal for the problem due to
the high-dimensional dataset that has been selected [8]. A
random forest model can be used to easily perform feature
selection and reduction, and thus will help understand which
metrics affect storms undergoing rapid intensification, which
may yield insightful analysis as to (if proven true) why rapid
intensification is increasing over time.

One challenge in building a proper supervised learning
model for this topic is that a lower percentage of storms
experience rapid intensification, thus leading to a potentially
misleading level of accuracy. For example, it is reported that
only 20%-30% of tropical storms in the Atlantic experience
rapid intensification, which means a classifier could answer
”No” and be correct 70%-80% of the time. Thus, our model
will account for the uneven amount of labeled data for RI
storms vs No-RI storms [7].

## Unsupervised
- **Goal:** cluster storm observations by atmospheric conditions to identify clusters associated with RI behavior and intensity progression.
- **Model 1: K-Means**
	- Fast, interpretable baseline partitioning by nearest centroid.
	- Limitation: hard assignments and tendency toward similarly sized clusters, potentially preventing RI clusters.
- **Model 2: Gaussian Mixture Model (GMM)**
	- Soft probabilistic assignment per observation.
	- Supports varying cluster size/shape, helping preserve smaller RI-prone regimes.
- **Model selection:** choose hyperparameters via elbow + silhouette (K-Means) and BIC (GMM).


---
[Back to Home]({{ '/' | relative_url }})
