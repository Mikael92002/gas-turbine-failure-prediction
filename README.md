# Gas Turbine Risk Modeling: ML and Feature Engineering for Failure Prediction (NASA C-MAPSS Dataset)
## *A replicable pipeline for estimating engine failure risk using sensor data (applicable to gas turbines like LM6000)*
Overview
A machine learning pipeline to predict Remaining Useful Life (RUL) of turbofan engines using sensor data. Achieves a NASA score of 10.60 with XGBoost, demonstrating applicability to gas turbine risk modeling (e.g., LM6000 maintenance prioritization).

Key Features:

Feature engineering: Lag/rolling features for sensor degradation patterns

Model comparison: Linear Regression, Random Forest, and XGBoost

Interpretable results: SHAP/feature importance for root-cause analysis

Table of Contents
Project Background

Dataset

Methodology

Results

How to Run

Future Work

License

Project Background
Predictive maintenance is critical for gas turbines (like LM6000) to:

Reduce unplanned downtime

Optimize maintenance schedules

Mitigate catastrophic failures

This project replicates a real-world scenario using NASA's C-MAPSS dataset, mirroring PROENERGY's need for data-driven turbine risk models.

Dataset
NASA C-MAPSS FD001:

100 training engines | 100 test engines

21 sensor channels (temperature, pressure, etc.)

Operational settings (3 variables)

Ground truth RUL provided for validation

