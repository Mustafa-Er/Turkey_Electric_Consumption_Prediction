# 🇹🇷 Turkey Electricity Consumption Prediction (Hourly-Based)

This project focuses on **forecasting hourly electricity consumption (TÜKETİM)** in Turkey using historical data, employing two different modeling approaches:

- **SARIMA (Seasonal ARIMA)**
- **Attention-Based LSTM (AT-LSTM)**

---

## 📊 Dataset Overview

- **Time Range**: January 2022 – March 2025  
- **Frequency**: Hourly  
- **Target Feature**: `TÜKETİM` (Consumption in MW)  
- **Additional Features**: `ÜRETİM`, `İTHALAT`, `İHRACAT`

### 🌀 Detected Seasonality

- **Daily Seasonality**: 24 hours  
- **Weekly Seasonality**: 168 hours

### 📌 Sample View of the Data

![Head & Tail of the Data](https://github.com/user-attachments/assets/1a045033-0b5c-4fa8-8aa6-d863006e1afe)

---

## 🧠 Models Used

### 1. SARIMA
- Classical time series model  
- Incorporates seasonal patterns using `seasonal_order = 24`

### 2. AT-LSTM (Attention-Based LSTM)
- Neural network with **LSTM** and **attention mechanism**
- **Window Size**: 48 hours (past 48 hours used to predict the next hour)
- Attention helps identify which time steps are most important to the prediction

---

## 📈 Evaluation Metrics

| **Model**  | **MAE (Mean Absolute Error)** | **R² Score** |
|------------|-------------------------------|--------------|
| AT-LSTM    | **325.10**                    | **0.99**     |
| SARIMA     | 3014.65                       | 0.56         |

> ⚠️ **AT-LSTM significantly outperformed SARIMA** in both accuracy and explanatory power.

---

## 🔍 Attention Insights

The attention mechanism revealed that the **most recent time steps** (especially the last few hours in the 48-hour input window) contribute most to the forecast:

![Attention Weights](https://github.com/user-attachments/assets/b53dc0fd-270f-4ef7-b76b-cde4691be359)

📌 This demonstrates the AT-LSTM model's ability to **capture short-term temporal dependencies**, improving the accuracy of electricity demand forecasting.

---

## ✅ Conclusion

- **SARIMA** is simple but limited in capturing nonlinear temporal relationships.
- **AT-LSTM** excels in detecting short-term patterns and offers **higher accuracy**.
- The attention mechanism provides **interpretability**, showing which past values influence the forecast the most.

This project illustrates the strength of combining **deep learning and attention mechanisms** in time series forecasting tasks.
