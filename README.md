# sales-forecasting-project

# Sales Forecasting using Time-Series Analysis

An end-to-end machine learning project that forecasts future daily sales for a retail superstore using historical data and an XGBoost model.

![Project Banner](https://i.imgur.com/8Q1bT1e.png)

## 1. Business Problem

Accurate sales forecasting is critical for business success, enabling optimized inventory management, resource allocation, and strategic financial planning. This project addresses this need by developing a predictive model that learns from past sales patterns, including trends and seasonality, to generate reliable future sales forecasts. The goal is to provide the business with a data-driven tool to anticipate demand and make informed decisions.

---

## 2. Dataset

The model is trained on the **Superstore Sales Dataset**, a clean and comprehensive transactional dataset sourced from Kaggle.

* **Source:** [Kaggle Dataset Link](https://www.kaggle.com/datasets/rohitsahoo/sales-forecasting)
* **Content:** Contains over 9,800 records of product sales from 2014 to 2017.
* **Key Columns:** `Order Date`, `Sales`.

---

## 3. Methodology & Key Techniques

This project implements a complete time-series forecasting workflow, focusing on creating a robust model from raw transactional data.

1.  **Data Preparation:** The dataset was loaded, and the `Order Date` column was parsed into a proper datetime format.
2.  **Time-Series Resampling:** Transactional data was aggregated into total **daily sales** to create a consistent time-series.
3.  **Feature Engineering:** To allow the model to understand time, new features were engineered directly from the `DatetimeIndex`:
    * `year`
    * `month`
    * `day`
    * `day_of_week`
    * `week_of_year`
    * `quarter`
4.  **Chronological Train-Test Split:** The data was split chronologically to simulate a real-world forecasting scenario. The model was trained on data from 2014-2016 and tested on unseen data from 2017.
5.  **Model Training:** An **XGBoost Regressor**, a powerful gradient boosting algorithm, was trained on the engineered features to predict the daily sales target.

---

## 4. Model Performance & Results

The final model demonstrated a strong ability to capture the underlying patterns in the sales data and produce an accurate forecast for the test year (2017).

* **Evaluation Metric:** The model's performance was measured using Root Mean Squared Error (RMSE).
* **Result:** The model achieved an **RMSE of $2,149.40**, indicating that, on average, the daily sales forecast was off by this amount.

The chart below visually confirms the model's success. The predicted sales (dashed orange line) effectively track the actual sales (solid blue line), capturing key seasonal trends, including the major sales spikes at the end of the year.

![Actual Sales vs. Forecasted Sales Chart](https://i.imgur.com/uG9nZ1n.png)

---

## 5. Technologies Used

* **Python 3**
* **Pandas:** For data manipulation, resampling, and feature engineering.
* **XGBoost:** For training the advanced gradient boosting model.
* **Scikit-learn:** For model evaluation (`mean_squared_error`).
* **Matplotlib:** For data visualization.
* **Jupyter Notebook / VS Code:** For the development environment.
