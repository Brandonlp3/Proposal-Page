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

## Method Overview
We employ two complementary approaches to study rapid
intensification (RI) in Atlantic hurricanes. The unsuper-
vised component clusters storm observations by their atmo-
spheric/environmental conditions to identify recurring regimes
and relate them to RI behavior. The supervised component
trains a predictive model to forecast whether RI will occur
over a specified future horizon. We will tune clustering and
classifier hyperparameters on validation data (silhouette/BIC
for clustering; trees/depth/class weights for random forest)
and evaluate with PR-AUC and F1/recall to handle class
imbalance [7]. Details of each approach, including model
choices, hyperparameter selection, and evaluation under class
imbalance, are provided in the sections below.

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
The unsupervised learning portion of this project will in-
volve clustering hurricanes by leveraging observations on their
atmospheric conditions to classify their progression. Further,
whether differing magnitudes of RI is represented within
specific atmospheric conditions.

The first candidate learning method is K-Means clustering,
which will partition storm observations into k clusters by
iteratively assigning each observation to the nearest centroid.
A limitation is that K-Means produces hard assignments
and assumes equal-sized clusters, raising concerns since the
smaller population of RI prone storm environments may be
absorbed into the conditions associated with that of a larger
neighboring cluster.

To address this, the second candidate learning method
is Gaussian Mixture Models (GMM), which assigns each
datapoint a probability of belonging to each cluster and, most
importantly, allows clusters to vary in size and density, making
it better suited to present differing scales of small distinct RI
prone storms. This soft assignment works to reduce the chance
of cluster absorption. For both methods, the hyperparameter
will be determined empirically using the elbow method and
silhouette scoring for K-Means, and BIC for GMM.


---
[Back to Home]({{ '/' | relative_url }})
