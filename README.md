# WALMART WEEKLY SALES FORECASTING

In today’s data-driven world, being able to predict the future isn’t just a competitive advantage, it’s a necessity. Whether it’s optimizing supply chains or preparing for seasonal demand surges, accurate forecasting can transform business strategies. In this project, I took a deep dive into Walmart’s weekly sales data to uncover patterns, understand seasonality, and build a forecasting model capable of predicting future sales for the next two years.

Dataset can be found at: https://www.kaggle.com/datasets/mikhail1681/walmart-sales

## Dataset Description:
This dataset contains weekly sales data across multiple Walmart stores. It includes features such as:

- Store: Store number
- Date: Weekly timestamps
- Weekly_Sales: Sales figures
- Holiday_Flag: Whether the week had a holiday
- Macroeconomic variables like Temperature, Fuel_Price, CPI, and Unemployment

## Project Overview:
This project walks through a complete forecasting workflow:

- Data cleaning and transformation
- Visualizing the trends
- Time Series stationarity test
- Time Series Decomposition
- Model Selection
- Model Building
- Model Forecasting
- Store Level Insights

## Results:
Due to the strong seasonal coponenent present in series, we used SARIMA model for forecasting.

<img width="1014" alt="Screenshot 2025-03-23 at 5 04 19 AM" src="https://github.com/user-attachments/assets/6768be7e-a723-44c7-a6fa-cc67edff3c66" />

The model captures seasonal patterns, as seen in the recurring peaks and fluctuations. The forecast follows the historical trend, but there is some variability in the predicted values. Significant sales spikes are observed in both historical and forecasted periods, suggesting seasonal demand fluctuations. The model appears to provide a reasonable projection of future sales, though uncertainty increases over time.

Store level forecasting

Instead of training a separate model for each store , which can become complex and noisy, especially for lower-volume or inconsistent stores , I made a strategic decision:
Use the aggregated SARIMA forecast as a baseline and proportionally distribute it to stores based on historical contribution

<img width="1002" alt="Screenshot 2025-03-23 at 5 07 53 AM" src="https://github.com/user-attachments/assets/4c59e6f5-9afd-4b17-a4f9-287116861d22" />

For most stores, the forecasted sales closely follow the level and seasonal patterns seen in the historical data, especially in stores like Store 1 and Store 10. The forecasts capture repeating annual spikes, suggesting the model has learned the seasonality. The transitions between observed and forecasted sections are smooth, indicating good continuity. However, because the same SARIMA model was used across stores with scaling, store-specific anomalies or unique trends may not be captured, especially in lower-volume stores like Store 30. Overall, the forecasts appear reasonable and consistent with past behavior, supporting the assumption that stores follow a common seasonal pattern.

## Technologies & Tools

- Python 3.x
- Pandas
- NumPy
- Matplotlib
- Statsmodels

## Use Cases

- Retail demand forecasting
- Inventory planning
- Time series modeling with seasonality
- Model interpretability and visual diagnostics

## Blog Link: 
https://medium.com/@gayatrigattani2001/forecasting-walmart-sales-with-sarima-from-aggregated-trends-to-store-level-insights-096dac8957cd
