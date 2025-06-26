# 🧾 Final Report: Seoul Bike Rental Demand Prediction

## 🎯 Project Goal

The goal of this project is to **predict hourly demand** for Seoul's public bike-sharing service (Ttareungi) using **weather conditions and time-based features**. By building an effective regression model, this project aims to support operational planning and resource allocation for the system.

---

## 📚 Dataset Summary

- **Bike Rental Data**: Hourly rental logs from June to August 2023, including rental times, stations, and distances.
- **Weather Data**: Daily weather observations for Seoul, including temperature, humidity, wind speed, rainfall, and sunlight hours.

> ⚠️ Large data files were excluded from Git and shared via [Google Drive](https://drive.google.com/drive/folders/1Xq1_BwaJTwwWs1QDhfQklecDNFyghps8?usp=drive_link).

---

## 🔍 Data Preprocessing & Feature Engineering

- **Merged** 3 months of rental data into one dataset.
- **Cleaned** missing values (`gender`, `birth_year`, `rainfall`, etc.).
- **Converted datetime** to extract:
  - Hour (`rental_hour`)
  - Weekday (`rental_weekday`)
  - Is weekend (`is_weekend`)
- **Weather Data Cleaned**:
  - Handled missing rainfall values by filling with `0`
  - Created temperature range feature (`temp_range`)
  - Created binary feature for rainy day (`rain_binary`)

---

## 📊 Exploratory Data Analysis (EDA)

Key findings:
- **Commuting Patterns**: Rental spikes at 8 AM and 6 PM
- **Weekdays vs Weekends**: Weekdays show higher rental counts
- **Temperature**: Rentals are generally spread over wide range temperature, but heavy rain overrides this
- **Rain**: Strong negative impact on rental count

---

## 🤖 Modeling

- **Target Variable**: `rental_count` (hourly aggregated)
- **Features**: Weather (`avg_temp`, `rain`, `humidity`, etc.) and time-based indicators (`hour`, `weekday`, etc.)
- **Models Tested**:
  - Random Forest
  - XGBoost (Base & Tuned)
  - SHAP for explainability

### 📈 Final Model: Tuned XGBoost

| Metric      | Score   | Ratio (to mean count ~5967) |
|-------------|---------|-----------------------------|
| MAE         | 962.43  | 16.13%                       |
| RMSE        | 1610.30 | 26.99%                       |

---

## 🔎 Feature Importance

### XGBoost Feature Importance (Gain-based)
Top predictors:
- `rental_hour_19`, `rental_hour_18`, `avg_temp_C`, `daily_rain_mm`

### SHAP Summary Insights
- **Rain** drastically reduces demand
- **Evening hours (6–8 PM)** are peak usage times
- **Temperature** has nonlinear influence

---

## 🖼️ Visualizations

> See all charts in `/images/` and in the [README.md](./README.md#-visualization-results)

---

## ✅ Conclusion

- **Weather has clear impact** on Seoul’s bike rental demand, especially rainfall and temperature.
- **Rental hour** also impact on Seoul’s bike rental demand -> Higher in commuting hour.
- **Tuned XGBoost** performed well, with interpretable SHAP values.
- The model can be used to help predict future demand and optimize bike placement or maintenance planning.

---

## 👨‍💻 Author

- **Name**: Minkyu Kim (김민규)  
- **GitHub**: [crunchy-child](https://github.com/crunchy-child)  
- **Date**: June 2025  