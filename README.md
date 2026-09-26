**Air Quality Data Analysis in Ho Chi Minh City**
Data analysis project assessing air pollution levels in Ho Chi Minh City (HCMC), Vietnam, using real sensor data from an air quality monitoring network.

## 📌 Overview

Air pollution is one of the most pressing public health and sustainability challenges facing large cities worldwide, and HCMC is no exception. This project analyzes air-quality and meteorological data collected from 6 monitoring stations across HCMC to:

- Clean and validate raw sensor data
- Detect and handle outliers
- Engineer derived features (season, AQI index)
- Analyze correlations between pollutants and weather conditions
- Visualize pollution trends and patterns
- Propose data-driven solutions to reduce air pollution

## 🗂️ Dataset

| | |
|---|---|
| Source | Air Quality Monitoring Network (collected by Vietnam National University & University College Dublin) |
| Stations | 6 monitoring stations across HCMC |
| Original size | 52,548 observations × 10 variables |
| Analysis dataset (Station 6) | 9,499 observations × 43 variables (after feature engineering) |
| Time range | Jan 2021 – Dec 2022 |
| Variables | PM2.5, PM10, SO₂, NO₂, CO, O₃, temperature, humidity, timestamp, station |

## ⚙️ Methodology

1. **Data collection & exploration** — load raw Excel files, inspect structure and variable types
2. **Preprocessing** — standardize column names/timestamps, impute missing values, remove duplicates
3. **Outlier detection & treatment** — IQR method + Isolation Forest (unsupervised ML)
4. **Standardization** — scale quantitative variables with `StandardScaler`
5. **Feature engineering** — build `Season` (rainy/dry) and `AQI` (per Vietnam's QĐ 1459/QĐ-TCMT 2019 standard, hourly & daily)
6. **Visualization & correlation analysis** — boxplot, scatter, line, bar, pie, clustered bar, violin, hexbin charts; Pearson/Spearman correlation heatmaps; VIF & Condition Index multicollinearity diagnostics

## 🔍 Key Findings

- Air quality in HCMC stays at a **moderate-to-poor** level for much of the year, worsening in the dry season (Dec–Apr) due to weaker wind and less rainfall to disperse pollutants
- **CO** contributes the largest average share among pollutants, followed by SO₂, NO₂, and O₃; **PM2.5**, though smaller in share, poses the greatest health risk
- **TSP–PM2.5** and **CO–SO₂** are strongly correlated pairs (r ≈ 0.96 and 0.81) even after removing seasonal/trend effects, indicating real shared-source relationships (dust and combustion sources) rather than seasonal noise
- Traffic and industrial/construction activity are the main drivers of pollution in the city

## 💡 Proposed Solutions

- Expand the automatic air-quality monitoring network and build an open environmental data portal
- Reduce traffic emissions: clean public transport, EV incentives, low-emission zones
- Tighten industrial/construction emission controls
- Increase urban green cover and smart urban planning
- Apply AI/IoT and Machine Learning for AQI forecasting and real-time pollution mapping
- Raise public awareness through a personal AQI-tracking app

## 🛠️ Tools & Libraries

- **Python** (Google Colab)
- `pandas`, `numpy` — data processing
- `scikit-learn` — StandardScaler, Isolation Forest
- `seaborn`, `matplotlib` — visualization
- `statsmodels` — VIF / multicollinearity diagnostics

## 📁 Repository Structure

```
├── data/               # raw & processed datasets
├── notebooks/          # Google Colab 
├── report/             # full project report (PDF)
└── README.md
```

## 📚 References

1. World Health Organization, *Ambient (outdoor) air pollution: Key facts*, WHO Fact Sheets, Oct 2024.
2. Nhân Dân điện tử, *Báo động đỏ ô nhiễm không khí ở các đô thị lớn*, Apr 2024.
3. Cơ quan Môi trường (CEM), *Kiến tạo mạng lưới quan trắc môi trường không khí hiện đại và đồng bộ*.
4. Quyết định 1459/QĐ-TCMT (2019) — Tổng cục Môi trường, Việt Nam.
