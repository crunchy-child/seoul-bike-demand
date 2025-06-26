# 🧭 Project Retrospective: Bike Rental Demand Prediction Based on Weather Data

This project aimed to build a machine learning model that predicts **Seoul's public bike rental demand (Ddareungi)** based on **weather conditions** such as temperature, rainfall, humidity, and wind speed.

---

## ✅ Summary of Progress

- **Data Preprocessing**
  - Combined three months of bike rental data (June to August)
  - Cleaned missing values and standardized column names to English
  - Removed unnecessary columns to reduce memory usage
  - Created new features (e.g. `rental_hour`, `is_weekend`, `temp_range`, `rain_binary`)

- **Weather Data Integration**
  - Used KMA daily weather data for Seoul
  - Filled missing rainfall values with 0 (indicating no rain)
  - Merged bike and weather datasets using date as key

- **EDA and Visualization**
  - Analyzed rental trends by hour, weekday, and weather conditions
  - Explored correlation between weather features and rental counts
  - Visualized feature importance and overall trends

- **Modeling**
  - Trained and tuned an **XGBoost Regressor**
  - Evaluation metrics:
    - **MAE**: 962.43
    - **RMSE**: 1610.30
    - Considering the **average rental count (~5967)**, the model achieves about **16% MAE**, indicating reasonably accurate predictions

- **Model Interpretation**
  - Used **feature importance** and **SHAP analysis**
  - Key features include `rental_hour`, `avg_temp_C`, and `is_weekend`
  - Helped understand which weather/time factors impact rental demand the most

---

## 💡 Key Learnings

- This project was a meaningful challenge to predict real-world demand by combining **time series and external (weather) variables**
- Managing large datasets and maintaining a clean, reproducible project structure on GitHub was an excellent practice
- While the model isn’t perfect, its interpretability and performance can support actionable insights (e.g. allocating bikes in advance of expected demand)
- It strengthened my experience in **EDA, feature engineering, machine learning, and Git-based project management**

---

## 🚀 Future Improvements

- Add more contextual features like public events, holiday flags, or location-based attributes
- Explore deep learning models or hybrid ensemble techniques
- Extend the project to support **real-time demand forecasting**
- Compare Seoul’s data with other major cities