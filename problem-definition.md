---
layout: default
title: Problem Definition
---

# Problem Definition

## Problem
RI in hurricanes is an increasingly common and unpre-
dictable phenomenon that is worsened due to rising sea
temperatures from climate change. RI remains very difficult to
forecast in terms of timing and magnitude [5], which can make
proper large-scale preparation difficult. Current physics-based
and numerical weather models struggle to capture subtle inner-
core dynamics in storms [6]. Minor parameterization errors can
result in major changes, which is where we hope a machine
learning model can bridge this gap.

## Motivation
(WIP AI Generated Below)
Rising sea temperatures linked to climate change increase the urgency of improving RI forecasts. Current physics-based and numerical weather models often struggle to capture subtle inner-core storm dynamics, and small parameterization errors can cause large forecast deviations [6].

Machine learning can complement these models by learning complex, non-linear relationships among atmospheric variables and potentially improving early warning signal quality for preparedness planning.

## Scope and Assumptions
(WIP AI Generated Below)
- Scope boundaries: Atlantic basin storms using historical HURDAT2 tracks and ERA5 reanalysis variables; focus is research-oriented forecasting and analysis, not operational deployment.
- Assumptions: RI is defined as an increase of at least 30 knots in 24 hours; selected atmospheric predictors capture core signals relevant to RI.
- Constraints: Class imbalance (RI events are relatively rare), temporal non-stationarity across decades, and dependence on data alignment quality between track and reanalysis records.

---
[Back to Home]({{ '/' | relative_url }})
