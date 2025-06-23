# 🚲 Seoul Public Bike (Ddareungi) Usage Analysis

This project analyzes Seoul's public bike system "Ddareungi" to identify  
**rental patterns by season, time of day, and weather**, and ultimately build a demand prediction model.

---

## 🗂️ Project Structure
```text
seoul-bike-demand/
├── data/
│   └── raw/                # Raw data files (excluded from Git)
│   └── processed/          # Processed data (cleaned/merged)
├── notebooks/              # Jupyter notebooks for analysis
├── images/                 # Output plots and visualizations
├── .gitignore              # Git ignore settings
├── requirements.txt        # Required Python libraries
├── README.md               # Project overview
```
---

## 📦 Data

### 🔹 Weather Data
- Weather data for Seoul in 2023.06 to 2023.08
- Included in the repository: `data/raw/OBS_ASOS_DD_20250622210229.csv`

### 🔸 Bike Rental Records
- Public bike rental history from 2023.06 to 2023.08 (~2.4GB total)
- Due to GitHub file size limits, these files are not included in the repo.
- You can download them via the link below:

📎 [Download from Seoul Open Data Plaza](https://data.seoul.go.kr/dataList/OA-15182/F/1/datasetView.do)

→ After downloading, please place the files in `data/raw/`.

---

## 🧰 Tech Stack

- Python (pandas, numpy, matplotlib, seaborn, etc.)
- Jupyter Notebook
- Git & GitHub
- VSCode

---

## 🚀 Progress Overview

- ✅ Collected and organized raw datasets
- ✅ Created GitHub repository and project structure
- ✅ Configured `.gitignore` for large files
- ✅ Stored large CSVs locally and prepared external download link
- ⬜ Begin EDA (Exploratory Data Analysis)
- ⬜ Merge datasets and preprocess features
- ⬜ Build demand prediction model

---

## 📌 Data Source

- Seoul Open Data Plaza: [https://data.seoul.go.kr](https://data.seoul.go.kr)
- KMA: [https://data.kma.go.kr](https://data.kma.go.kr/)

---

## 🙋‍♂️ About Me

- Name: Minkyu Kim
- GitHub: [@crunchy-child](https://github.com/crunchy-child)
