# Household_Energy_Forecasting
# Household Energy Consumption Forecasting

## 📌 Objective

Forecast short-term household energy usage using historical time-based patterns and compare the performance of different models.

## 📂 Dataset

**Dataset:** Household Power Consumption Dataset
**Source:** [Kaggle](https://www.kaggle.com/datasets/uciml/electric-power-consumption-data-set)

* Contains 2+ million observations of household energy usage (2006-2010).
* Key column for forecasting: `Global_active_power`.
* Other features: `Global_reactive_power`, `Voltage`, `Global_intensity`, `Sub_metering_1`, `Sub_metering_2`, `Sub_metering_3`.

## 🛠️ Steps Completed

1. **Data Loading & Preprocessing**

   * Converted `Date` and `Time` into `Datetime`.
   * Set `Datetime` as index.
   * Converted `Global_active_power` to numeric and handled missing values.

2. **Time Series Resampling**

   * Resampled data to **daily averages** to reduce noise and capture trends.
   * Visualized daily energy consumption.

3. **Feature Engineering (for XGBoost)**

   * Created lag features (`Lag_1`, `Lag_7`) to capture autocorrelation.
   * Added time-based features: `Day`, `Month`, `Year`, `Weekday`.

4. **Train-Test Split**

   * Used last **30 days as test data** for short-term forecasting.
   * Ensured temporal split (no random shuffle).

5. **Modeling**

   * **ARIMA**: Captures linear trends and autocorrelation.
   * **Prophet**: Captures trend and seasonal components.
   * **XGBoost**: Handles nonlinear patterns with lag and time features.

6. **Evaluation Metrics**

   * Mean Absolute Error (MAE)
   * Root Mean Squared Error (RMSE)

| Model   | MAE   | RMSE  |
| ------- | ----- | ----- |
| ARIMA   | 0.250 | 0.306 |
| Prophet | 0.213 | 0.296 |
| XGBoost | 0.204 | 0.268 |

7. **Visualization**

   * Plotted **actual vs forecasted energy usage** for each model.
   * Combined plot for **model comparison**.

## 📊 Insights

* **XGBoost** performed best for short-term forecasting due to its ability to capture nonlinear dependencies and short-term patterns.
* **Prophet** captured seasonality effectively, useful for weekly and yearly trends.
* **ARIMA** provided a reasonable baseline but struggled with nonlinear fluctuations.
* Feature engineering (lag features and time features) significantly improved XGBoost performance.

## ✅ Conclusion

In this task, I successfully forecasted household energy consumption using historical data. I compared three models—ARIMA, Prophet, and XGBoost—evaluating them with MAE and RMSE metrics. XGBoost performed best for short-term forecasting, while Prophet captured seasonal trends effectively. This study demonstrates the importance of feature engineering and model selection in time series forecasting, providing actionable insights for energy management and smart grid planning.

## 🧰 Skills Gained

* Time series forecasting
* Feature engineering for temporal data
* Model comparison and evaluation using MAE and RMSE
* Temporal data visualization

## 📁 File Structure

```
Household_Energy_Forecast.ipynb   # Main Jupyter/Colab notebook
household_power_consumption.txt    # Dataset file
README.md                          # Project summary
```
