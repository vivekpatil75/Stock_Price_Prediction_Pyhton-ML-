#  Stock Price Prediction using Machine Learning

## Project Overview
This project focuses on predicting stock **closing prices** using historical data and various machine learning regression models. The goal is to compare different algorithms to find the most accurate one for stock price forecasting.


##  Data Overview

- **Source**: Fetched using `yfinance` python library.
- **Time Period**: January  1997 — August  2023
- **Columns**:
  -  `Open`, `High`, `Low`, `Close`, `Volume`, `Dividends`, `Stock Splits`
- **Target Variable**: `Close` price (to be predicted)

---

##  Technologies Used

- Python 3.x
- `pandas`, `numpy` for data manipulation
- `scikit-learn` for machine learning models
- `matplotlib`, `seaborn` for visualization
- `yfinance` for data extraction

---

##  Data Preprocessing Steps

1. **Data Collection**  
   - Fetched historical stock data using `yfinance` python library.

2. **Initial Cleaning**
   - Removed unnecessary columns like `Dividends` and `Stock Splits`.
   - Converted `Date` to datetime and set as index.

3. **Feature Selection**
   - Used features: `Open`, `High`, `Low`, `Volume`
   - Target: `Close`

4. **Train-Test Split**
   - Data split into **80% training** and **20% testing**.

5. **Feature Scaling**
   - Applied `StandardScaler` to normalize the data.

---

## Machine Learning Models Used

| Model                   | R² Score       | MSE       | MAE     |
|------------------------|----------------|-----------|---------|
| Linear Regression       | **0.99990**    | **2.06**  | **0.83**|
| Random Forest Regressor| 0.99983        | 3.41      | 1.08    |
| Bagging Regressor      | 0.99983        | 3.44      | 1.08    |
| Decision Tree Regressor| 0.99969        | 6.29      | 1.41    |
| AdaBoost Regressor     | 0.99719        | 57.88     | 6.35    |

---

##  Key Insights

- **Linear Regression** surprisingly performed the best, likely due to the strong linear pattern in the stock data.
- **Random Forest and Bagging** performed nearly as well, confirming robustness.
- **AdaBoost** showed significantly higher error, possibly due to its sensitivity to noise and outliers.
- High R² scores across all models suggest that the dataset has strong predictive patterns.

---

##  Conclusion

- This project demonstrates that **simple linear models** can outperform complex ensemble models in certain stock price prediction scenarios.
- However, results depend heavily on **data characteristics**, and non-linear models might generalize better on different datasets or time frames.
- For real-world deployment, further steps like **cross-validation**, **feature engineering**, and **time-series-aware models** (e.g., LSTM, ARIMA) could improve results.

---






