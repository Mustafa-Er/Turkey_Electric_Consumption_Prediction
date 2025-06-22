# 🇹🇷 Turkey Electricity Consumption Prediction (Hourly-Based)
This project focuses on forecasting hourly electricity consumption (TÜKETİM) in Turkey using historical data and applying two different modeling approaches:

SARIMA (Seasonal ARIMA)

Attention-Based LSTM (AT-LSTM)

📊 Dataset Overview
Time range: January 2022 to March 2025

Frequency: Hourly

Target Feature: TÜKETİM (Consumption in MW)

Additional Features: ÜRETİM, İTHALAT, İHRACAT

Detected Seasonality:

Daily: 24 hours

Weekly: 168 hours

Example head and tail of the data:

yaml
Kopyala
Düzenle
Head:
TARİH               | ÜRETİM | İTHALAT | İHRACAT | TÜKETİM
2022-01-01 01:00:00 | 5016   | 31200.95| 353.34  | 31020.29
...

Tail:
2025-03-12 00:00:00 | 10175  | 39085.15| 42.47   | 38532.23
🧠 Models Used
1. SARIMA
A classical time series model incorporating seasonality (seasonal order = 24 hours).

2. AT-LSTM (Attention-Based LSTM)
Utilized a window size of 48 hours (i.e., last 48 hourly steps used to predict the next step).

Integrated an Attention Mechanism to learn which past time steps contribute most to the current prediction.

📈 Evaluation Metrics
Model	MAE (Mean Absolute Error)	R² Score
AT-LSTM	325.10	0.99
SARIMA	3014.65	0.56

⚠️ The AT-LSTM model significantly outperforms SARIMA in both error reduction and predictive power.

🔍 Attention Insights
The attention visualization indicates that the most recent time steps (especially the last few hours in the 48-hour window) have the highest impact on the model’s prediction:


This shows the AT-LSTM model is capable of identifying and leveraging short-term temporal patterns effectively.


