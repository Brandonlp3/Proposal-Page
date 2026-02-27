---
layout: default
title: Introduction / Background
---

# Introduction / Background

## Topic Overview
RAPID intensification (RI) is a phenomenon in which a
tropical system’s maximum wind speed increases by at
least 30 knots within a 24-hour period, often in an environment
of low wind shear, higher relative humidity, and higher sea
surface temperatures [1]. Numerous applications of machine
learning have been used to forecast hurricanes and RI. For
example, support vector machines (SVMs) have been applied
to classify tropical cyclone formations, mapping meteoro-
logical parameters with storm development [2]. Similarly,
neural networks such as multilayer perceptrons (MLPs) have
been used to model non-linear relationships between such
parameters to identify atmospheric thresholds that lead to RI
in storms [3].

This project involves timeseries data on recorded Atlantic
tropical storms. The first dataset is HURDAT2 track data con-
taining 6-hour storm records, including geographic position,
maximum sustained wind speed, and central pressure. The
second dataset is ERA5 global reanalysis data since 1940,
which we will confine to the Atlantic Ocean. The relevant
features utilized include sea surface temperatures, vertical
wind shear, mean sea level pressure, and relative mid-level
humidity, which are features known to contribute to hurricane
intensity [4].


---
[Back to Home]({{ '/' | relative_url }})
