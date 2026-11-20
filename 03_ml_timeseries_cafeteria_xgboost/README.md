# Cafeteria Meal Demand Forecasting & Behavioral Feature Analysis

**Author**: Jin Hwang (`황진`), Department of Artificial Intelligence, Konyang University (`건양대학교 인공지능학과`)
**Date**: `2025-06-19`
**Original Korean Title**: `구내식당 식수 인원 예측 및 데이터 분석`

## Summary

Tabular time-series demand forecasting across multi-year institutional cafeteria records (`2016–2021`) using gradient-boosted regression (`XGBoost`) and engineered workforce attendance predictors (overtime hours, night shifts, leave ratios, business travel, remote work counts, and calendar features).

- **Lunch Forecast (`중식계`)**: `MAE = 84.49` across test horizon.
- **Dinner Forecast (`석식계`)**: `MAE = 45.86` across test horizon.
- **Interpretability Finding**: Workforce operational variables (`시간외근무강도`, `야간근무건수`, `휴가자수`) strongly dominate menu presence flags in average feature importance.

## Repository Contents

| File | Description |
| :--- | :--- |
| [cafeteria_demand_prediction_presentation.pdf](./cafeteria_demand_prediction_presentation.pdf) | 26-slide analytical presentation (`2025-06-19`) covering dataset schema, preprocessing, modeling, and error analysis |
| [actual_vs_predicted_timeseries.png](./actual_vs_predicted_timeseries.png) | Dual time-series comparison of actual vs. predicted Lunch (`MAE 84.49`) and Dinner (`MAE 45.86`) attendance |
| [xgboost_feature_importance.png](./xgboost_feature_importance.png) | Mean feature-importance bar chart across 15 engineered predictors |
