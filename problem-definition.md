---
layout: default
title: Problem Definition
---

# Problem Definition

## Problem
Rapid intensification (RI) in hurricanes is increasingly common and remains difficult to forecast in both timing and magnitude [5]. The project frames this as a machine learning problem:

- Supervised task: Binary classification of whether a storm will undergo RI within a future window (for example, 24 hours).
- Unsupervised task: Clustering storm environments to identify atmospheric regimes associated with RI behavior.

## Motivation
Rising sea temperatures linked to climate change increase the urgency of improving RI forecasts. Current physics-based and numerical weather models often struggle to capture subtle inner-core storm dynamics, and small parameterization errors can cause large forecast deviations [6].

Machine learning can complement these models by learning complex, non-linear relationships among atmospheric variables and potentially improving early warning signal quality for preparedness planning.

## Scope and Assumptions
- Scope boundaries: Atlantic basin storms using historical HURDAT2 tracks and ERA5 reanalysis variables; focus is research-oriented forecasting and analysis, not operational deployment.
- Assumptions: RI is defined as an increase of at least 30 knots in 24 hours; selected atmospheric predictors capture core signals relevant to RI.
- Constraints: Class imbalance (RI events are relatively rare), temporal non-stationarity across decades, and dependence on data alignment quality between track and reanalysis records.

---
[Back to Home]({{ '/' | relative_url }})
