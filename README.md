# HDFC Stock Price Prediction using ARIMA, XGBoost and LSTM

This project predicts the stock price of HDFC Bank using three models: ARIMA (Auto-Regressive Integrated Moving Average) and XGBoost (Extreme Gradient Boosting) and LSTM (Long Short-Term Memory). The dataset contains historical stock prices, and we perform the following tasks:

- Exploratory Data Analysis (EDA)
- Data Preprocessing
- Training the ARIMA model
- Training the XGBoost model
- Training the LSTM model
- Evaluation and forecasting of future stock prices

## Project Structure

```
├── HDFCBANK.csv                                            # Dataset file
├── Stock_Price_Prediction_Model_ARIMA_XGBOOST_LSTM.ipynb   # Jupyter Notebook containing the code
└── README.md                                               # This README file
```

## Requirements

To run this project, you need the following libraries:

```
pip install pandas numpy matplotlib seaborn statsmodels xgboost scikit-learn
```

## Dataset

The dataset used in this project is `HDFCBANK.csv`, which contains the following columns:

- **Date**: Date of stock data

- **Open**: Opening price

- **High**: Highest price during the day

- **Low**: Lowest price during the day

- **Close**: Closing price at the end of the day

- **Volume**: Number of shares traded

- **Adj Close**: Adjusted closing price

## Steps

## 1. Exploratory Data Analysis (EDA)

We start by loading the dataset and visualizing the closing prices over time. We also check for any missing values and handle them.

## 2. ARIMA Model

**2.1 Preprocessing for ARIMA**

The time series data is differenced to make it stationary, and the data is split into training and testing sets.

**2.2 Training the ARIMA Model**

We fit the ARIMA model on the training data and print the model summary.

**2.3 Forecasting and Evaluation**

The model is used to forecast future stock prices, and we evaluate the performance using Mean Squared Error (MSE) and Mean Absolute Error (MAE).

## 3. XGBoost Model

**3.1 Preprocessing for XGBoost**

For XGBoost, we create features like Year, Month, Day, DayOfWeek, etc., and split the dataset into training and testing sets.

**3.2 Training the XGBoost Model**

We train the XGBoost model on the features and target (closing price).

**3.3 Forecasting and Evaluation**

The model is used to predict stock prices, and the performance is evaluated using MSE and MAE.

## 4. LSTM Model

**4.1 Preprocessing for LSTM**

For LSTM, we perform scaled_data and scaled features

**4.2 Create training and testing datasets**

We create sequences of data for the LSTM model.

**4.3 Create training and testing**

We create training and testing datasets for the LSTM model.

**4.4 Build LSTM model**
We build the LSTM model with the specified parameters.

## Conclusion

## ARIMA (AutoRegressive Integrated Moving Average)

- **Best for**: Time series forecasting when the data shows clear temporal dependence.
- **Advantages**: Simplicity, interpretability, and works well with stationary data.
- **Limitations**: Assumes linear relationships and stationarity, may not handle non-linear patterns well, especially in stock price prediction.
- **When to use**: If the data shows clear trends and seasonality, and the dataset is relatively small.

---

## XGBoost (Extreme Gradient Boosting)

- **Best for**: Predicting stock prices using engineered features such as lagged values, moving averages, etc.
- **Advantages**: Handles non-linear relationships, works well with large datasets, and performs well on a wide range of problems.
- **Limitations**: Requires careful feature engineering and hyperparameter tuning.
- **When to use**: If you have rich, engineered features and a larger dataset. It's great at leveraging non-linear relationships.

---

## LSTM (Long Short-Term Memory)

- **Best for**: Predicting time series data with complex, long-range dependencies (which is common in stock prices).
- **Advantages**: LSTM can capture non-linear relationships and long-term dependencies, making it ideal for sequential data like stock prices.
- **Limitations**: Requires larger datasets, more computational resources, and can be more challenging to fine-tune.
- **When to use**: If you're dealing with large amounts of sequential data and want to capture both short- and long-term dependencies in stock prices.

---

## Why LSTM May Be Better Than ARIMA and XGBoost

1. **Sequential Dependencies**: Stock prices often depend on long-term patterns and complex relationships that LSTM models can capture well. In contrast, ARIMA might only capture short-term dependencies, and XGBoost might struggle with time-based sequence modeling without explicit feature engineering.
2. **Non-linearity**: Stock market data tends to have non-linear patterns. XGBoost and LSTM are better at modeling such patterns, while ARIMA is primarily linear.

3. **Learning from Data**: LSTM can learn the underlying patterns directly from the data, while ARIMA requires pre-processing and assumptions about stationarity, and XGBoost needs careful feature engineering.

---

## In Summary:

- **ARIMA**: Works well for simpler time series data where trends and seasonality are the main drivers.
- **XGBoost**: Works well when there are engineered features that provide strong predictive signals.
- **LSTM**: Best suited for capturing complex dependencies and non-linear relationships in time series data, making it potentially more powerful for stock price prediction, especially if you have enough data.

---

## Suggested Approach:

1. **Step 1**: Start with ARIMA to baseline your performance and understand the simpler linear patterns.
2. **Step 2**: Try XGBoost with engineered features to see if you can improve accuracy.
3. **Step 3**: Finally, implement LSTM to capture more complex patterns, especially if your dataset is large enough and the relationships are non-linear.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
