# Feature Description: Smart Factory Energy Prediction Challenge

This document provides detailed descriptions of all features used in building the regression model to predict equipment_energy_consumption. The features were selected based on exploratory data analysis, correlation, variance checks, and model importance scores.

## Target Variable

**equipment_energy_consumption:**
Continuous variable representing the amount of energy consumed by the equipment at a given timestamp.
**Type:** float
**Role:** Target variable

## Temporal Feature
**timestamp:**
Date and time of the recorded measurement. This feature was transformed to extract:

**hour:** Hour of the day (0–23)
**day_of_week:** Day of the week (0=Monday, 6=Sunday)

These derived features help capture temporal patterns in energy usage.

**Type:** datetime → int (after feature engineering)


## Environmental Sensor Readings (Zone-wise)
These features represent temperature and humidity recorded in 9 zones of the facility. They help capture localized environmental conditions affecting equipment performance.

**zone_1_temperature** to **zone_9_temperature**
Zone-wise temperature in Celsius.
**Type:** float

**zone_1_humidity** to **zone_9_humidity**
Zone-wise relative humidity (%).
**Type:** float


## External Weather Conditions
These features come from outdoor weather stations and provide context for the indoor environment.

**outdoor_temperature**
Outdoor temperature in Celsius.
**Type:** float

**outdoor_humidity**
Outdoor relative humidity (%).
**Type:** float

**outdoor_pressure**
Atmospheric pressure in hPa.
**Type:** float

**wind_speed**
Wind speed (likely in m/s or km/h).
**Type:** float

**wind_direction**
Direction from which wind is blowing (in degrees).
**Type:** float

**dew_point**
Calculated dew point, indicative of saturation and moisture in the air.
**Type:** float

**weather_condition_index**
A categorical index encoding weather conditions such as sunny, cloudy, rainy. Used as a numeric categorical feature.
**Type:** int


**Random Variables**
*random_variable1* and *random_variable2*
After correlation and permutation importance analysis, these variables showed negligible predictive power. Hence, they were excluded from the final model.

**Role:** Discarded during feature selection
**Type:** float
