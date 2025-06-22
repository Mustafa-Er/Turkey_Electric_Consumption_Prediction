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

![image](https://github.com/user-attachments/assets/1a045033-0b5c-4fa8-8aa6-d863006e1afe)

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

![image](https://github.com/user-attachments/assets/b53dc0fd-270f-4ef7-b76b-cde4691be359)



This shows the AT-LSTM model is capable of identifying and leveraging short-term temporal patterns effectively.


