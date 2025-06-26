## 🧾 Final Thoughts

This project explored how weather conditions influence the hourly demand of Seoul’s public bike-sharing system, Ttareungi. Through meticulous data cleaning, feature engineering, and model development, I uncovered meaningful patterns and built an effective demand prediction pipeline.

### 🔍 Key Takeaways

- **Rainfall and temperature** had the most noticeable impact on rental volume. Rainy days sharply decreased demand.
- **Hourly patterns** were clear, with peaks around commuting times (8AM and 6–7PM).
- **XGBoost Regressor** yielded solid results:
  - MAE: **962.43** (≈16.13% of average hourly rentals)
  - RMSE: **1610.30**
- **SHAP analysis** provided interpretability, helping validate which features most influence predictions.

### ✅ What Went Well

- Successfully merged and processed **3 large-scale rental datasets** with **daily weather data**
- Built reusable pipelines for EDA, feature creation, and model training
- Achieved interpretable and reasonably accurate predictions
- Structured the project for **clear reproducibility and GitHub sharing**

### 🚀 Future Directions

- Extend weather data to **hourly granularity** for higher precision
- Add contextual factors such as **public holidays, events, or bike station locations**
- Explore **real-time prediction** using streaming weather APIs
- Build a **dashboard** to visualize predicted vs. actual demand

---

This project demonstrates how data-driven approaches can support urban mobility planning and demand management for smart cities.