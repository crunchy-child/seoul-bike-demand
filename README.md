# 🚲 Seoul Bike Rental Demand Prediction

## 📌 Project Overview

This project aims to predict hourly rental demand of Seoul's public bike system (Ttareungi) using weather data and time-related features. We analyze how weather conditions impact bike usage and build predictive models for accurate rental forecasting.

---

## 📁 Dataset

- **Bike rental data**: Hourly rental logs from June to August 2023 from Seoul Open Data Plaza
- **Weather data**: Daily weather observations for Seoul from the Korea Meteorological Administration (KMA)

### 📦 Datasets included in `.gitignore`
- 📎 [Download from Google Drive](https://drive.google.com/drive/folders/1Xq1_BwaJTwwWs1QDhfQklecDNFyghps8?usp=drive_link)
    
    → After downloading, please place the files `seoul_bike_rentals_2306.csv`, `seoul_bike_rentals_2307.csv`, `seoul_bike_rentals_2308.csv` in `data/raw/`.

    → After downloading, please place the files `bike_with_weather.csv`, `merged_bike_data.csv` in `data/processed/`.


---

## 🔍 Exploratory Data Analysis (EDA)

- **Hourly Patterns**: Peaks at 8 AM and 6 PM (commuting hours)
- **Weekdays vs Weekends**: Higher rentals on weekdays
    - When simply comparing counts, the number of weekends is smaller than the number of weekdays, so weekdays show higher rental counts.
- **Average Temp vs Daily Rental Count**: Evenly spread, but with low rental counts between 22 and 26 degrees.
    - It is estimated that it was likely rainy between 22 and 26 degrees.

---

## 🧪 Modeling

- **Target**: `rental_count` (hourly aggregated)
- **Features**: Weather (temp, rain, humidity...), time (hour, weekday, weekend)
- **Model**: XGBoost Regressor

| Metric | Score |
|--------|-------|
| MAE    | 962.43 |
| RMSE   | 1610.30 |
| MAE Rate | 16.13% |
| RMSE Rate | 26.99% |

---

## 🔎 Feature Importance & Explainability

### 📊 XGBoost Feature Importance (Gain-based)

Top Features:
- `rental_hour_19`
- `rental_hour_18`
- `avg_temp_C`
- `daily_rain_mm`
- `is_weekend`
- `avg_humidity_pct`

### 🧠 SHAP Summary

Key insights:
- Rain and average temperature strongly influence rental count
- Rentals are much lower during heavy rain
- At 7PM, 6PM, 5PM, 8AM shows high rental counts (commuting hour)

---

## 📂 Repository Structure
```text
seoul-bike-demand/
├── data/
│ └── processed/
│   ├── bike_with_weather.csv
│   ├── hourly_count_with_weather.csv ← used for modeling
│   └── merged_bike_data.csv
│ └── raw/
│   ├── seoul_bike_rentals_2306.csv
│   ├── seoul_bike_rentals_2307.csv
│   ├── seoul_bike_rentals_2308.csv
│   └── seoul_weather.csv
├── images/
│   ├── Average Temperature vs Daily Rental Count.png
│   ├── Bike Rentals Weekend vs Weekday.png
│   ├── Correlation between features and rental count.png
│   ├── Number of Bike Rentals by Hour.png
│   ├── Number of Bike Rentals by Weekday.png
│   ├── Random Forest Feature Importances.png
│   ├── Tuned XGBoost Actual vs Predicted.png
│   ├── Tuned XGBoost SHAP.png
│   ├── XGBoost Actual vs Predicted.png
│   ├── XGBoost Distribution of Residuals.png
│   └── XGBoost Feature Importances(Frequency Based).png
├── notebooks/
│   ├── 01_eda.ipynb
│   ├── 02_merge_weather.ipynb
│   ├── 03_eda_advanced.ipynb
│   └── 04_modeling.ipynb
├── results/
│   ├── Retrospective_Report.md
│   └── Final_Report.md
├── README.md
├── .gitignore
└── requirements.txt
```

---

## 📊 Visualization Results

### 🔹 Average Temperature vs Daily Rental Count
![Average Temperature vs Daily Rental Count](images/Average%20Temperature%20vs%20Daily%20Rental%20Count.png)

### 🔹 Bike Rentals: Weekend vs Weekday
![Bike Rentals Weekend vs Weekday](images/Bike%20Rentals%20Weekend%20vs%20Weekday.png)

### 🔹 Correlation between Features and Rental Count
![Correlation](images/Correlation%20between%20features%20and%20rental%20count.png)

### 🔹 Number of Bike Rentals by Hour
![Rentals by Hour](images/Number%20of%20Bike%20Rentals%20by%20Hour.png)

### 🔹 Number of Bike Rentals by Weekday
![Rentals by Weekday](images/Number%20of%20Bike%20Rentals%20by%20Weekday.png)

### 🔹 Random Forest Feature Importances
![RF Importance](images/Random%20Forest%20Feature%20Importances.png)

### 🔹 Tuned XGBoost: Actual vs Predicted
![Tuned XGB Prediction](images/Tuned%20XGBoost%20Actual%20vs%20Predicted.png)

### 🔹 Tuned XGBoost SHAP
![Tuned SHAP](images/Tuned%20XGBoost%20SHAP.png)

### 🔹 XGBoost: Actual vs Predicted
![XGBoost Prediction](images/XGBoost%20Actual%20vs%20Predicted.png)

### 🔹 XGBoost Distribution of Residuals
![Residuals](images/XGBoost%20Distribution%20of%20Residuals.png)

### 🔹 XGBoost Feature Importances (Frequency Based)
![XGBoost Importance](images/XGBoost%20Feature%20Importances(Frequency%20Based).png)

---

## ✍️ Conclusion

- Weather factors, especially rainfall, temperature and average humidity, significantly affect bike usage
- XGBoost achieved reasonable accuracy for predicting hourly demand
- SHAP values helped uncover key feature interactions

This project serves as a solid foundation for operational demand forecasting and resource allocation for Seoul’s bike-sharing system.

---

## 🔗 Author

Minkyu Kim (김민규)  
GitHub: [crunchy-child](https://github.com/crunchy-child)  
Project Period: June 2025
