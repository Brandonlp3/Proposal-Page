---
layout: default
title: Introduction / Background
---

# Introduction / Background

## Topic Overview
Rapid intensification (RI) is a phenomenon in which a tropical system's maximum wind speed increases by at least 30 knots within a 24-hour period, often in environments with low wind shear, higher relative humidity, and higher sea surface temperatures [1].

Forecasting RI remains difficult due to non-linear atmospheric interactions and subtle storm dynamics. This project studies historical Atlantic tropical storms and develops machine learning approaches to forecast RI and analyze long-term trends.

## Literature Review
### Source 1
- Citation key: [1] Kaplan et al.
- Summary: Defines and characterizes RI conditions and provides baseline meteorological context.
- Relevance to your project: Establishes the RI threshold and physical variables used in this project.

### Source 2
- Citation key: [2] Wei et al.
- Summary: Applies support vector machines (SVMs) to classify tropical cyclone formation using meteorological parameters.
- Relevance to your project: Supports the use of supervised ML for cyclone-related classification tasks.

### Source 3
- Citation key: [3] Xu et al.
- Summary: Uses multilayer perceptrons (MLPs) to model non-linear atmospheric relationships for RI-related behavior.
- Relevance to your project: Motivates neural and non-linear models for RI prediction.

Additional background reference: Ganesh et al. [4] identifies variables such as sea surface temperature, wind shear, pressure, and humidity as key predictors of hurricane intensity.

## Dataset Description
- Dataset name: HURDAT2 Atlantic tropical cyclone track dataset
- Data source: NOAA/NHC HURDAT2 archive
- Number of samples: 6-hourly storm records (exact count to be finalized after preprocessing)
- Number of features: Includes storm position, maximum sustained wind speed, and central pressure (plus engineered temporal features)
- Feature types: Time-series numerical geophysical variables
- Label/target definition: Binary RI label indicating whether wind speed increases by at least 30 knots within 24 hours

- Dataset name: ERA5 global reanalysis dataset (Atlantic subset)
- Data source: ECMWF ERA5 reanalysis
- Number of samples: Gridded historical atmospheric observations since 1940 (subset aligned to HURDAT2 storm windows)
- Number of features: Sea surface temperature, vertical wind shear, mean sea level pressure, relative mid-level humidity, and related predictors
- Feature types: Time-indexed numerical meteorological variables
- Label/target definition: Used as predictor input aligned with HURDAT2-based RI targets

## Dataset Link
- HURDAT2: https://www.nhc.noaa.gov/data/
- ERA5: https://cds.climate.copernicus.eu/

---
[Back to Home]({{ '/' | relative_url }})
