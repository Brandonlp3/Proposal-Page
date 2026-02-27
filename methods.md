---
layout: default
title: Methods
---

# Methods
(WIP I Just had AI make this short breakdown)
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

## Why These Methods
- K-Means provides an interpretable first pass at partitioning atmospheric storm states, with cluster count selected using elbow and silhouette analysis.
- GMM provides soft probabilistic assignments and flexible cluster shapes/sizes, reducing the risk that RI-prone minority patterns are absorbed by larger clusters.
- Random Forest is well-suited to high-dimensional meteorological predictors, supports feature importance analysis, and handles non-linear interactions.
- Logistic Regression provides a transparent baseline for comparison of discriminative performance.

Additionally, the supervised experiment design trains on older data (approximately 20-30 years ago) and evaluates on recent years to test both predictive generalization and the hypothesis of increasing RI frequency over time.


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

## Libraries / Packages
- scikit-learn: `KMeans`, `GaussianMixture`, `RandomForestClassifier`, `LogisticRegression`, and metrics utilities
- pandas / xarray: tabular and gridded time-series data preparation
- numpy: numerical preprocessing and feature construction

---
[Back to Home]({{ '/' | relative_url }})
