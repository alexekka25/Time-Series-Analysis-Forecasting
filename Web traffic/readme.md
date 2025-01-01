# Website Traffic Forecasting

This project aims to forecast website traffic using time series analysis techniques. It involves preprocessing the data, analyzing the time series, visualizing the trends, and applying machine learning and deep learning models for accurate predictions.

---

## Table of Contents
1. [Project Overview](#project-overview)
2. [Dataset Description](#dataset-description)
3. [Methodology](#methodology)
4. [Visualization](#visualization)
5. [Models Implemented](#models-implemented)
6. [Results](#results)
7. [Conclusion](#conclusion)

---

## Project Overview
Website traffic forecasting is essential for understanding user engagement, predicting server loads, and planning marketing campaigns. This project utilizes classical statistical models like ARIMA and modern deep learning models such as LSTM to forecast website visits based on historical data.

---

## Dataset Description
The dataset contains 232 rows with the following columns:
- **Date**: The date of the traffic record.
- **Visits**: The number of website visits on that date.

### Data Characteristics:
- The data spans multiple months, with daily granularity.
- Missing and inconsistent date formats were identified and handled during preprocessing.

---

## Methodology

### 1. **Data Preprocessing**
- **Date Parsing**: Handled multiple date formats (e.g., `MM-DD-YYYY`, `M/DD/YYYY`) and converted them into a consistent `YYYY-MM-DD` format.
- **Handling Missing Values**: Rows with invalid or missing dates (`NaT`) were dropped.
- **Normalization**: Scaled the `Visits` column for model compatibility.

### 2. **Stationarity Testing**
- Performed Augmented Dickey-Fuller (ADF) tests to check for stationarity.
- Applied transformations (logarithm and differencing) to make the time series stationary.

### 3. **Visualization**
- Line plots to display overall trends in website visits.
- Seasonal Decomposition of Time Series (STL) to analyze trend, seasonality, and residuals.
- ACF and PACF plots for model parameter identification.

---

## Models Implemented

### 1. **ARIMA (AutoRegressive Integrated Moving Average)**
- Parameters (p, d, q) were selected based on ACF and PACF plots and grid search.
- Evaluated model performance using Mean Absolute Error (MAE), Mean Squared Error (MSE), Root Mean Squared Error (RMSE), and Mean Absolute Percentage Error (MAPE).

### 2. **LSTM (Long Short-Term Memory)**
- Designed a sequential model with LSTM layers for capturing long-term dependencies in the time series.
- Preprocessed data to create sequences and reshaped it into the required 3D input format (samples, timesteps, features).
- Optimized hyperparameters such as number of neurons, epochs, and batch size.

---

## Results

### ARIMA
- **MAE**: 381.89
- **MSE**: 229,995.51
- **RMSE**: 479.58
- **MAPE**: 13.93%

### LSTM
- **MAE**: 412.69
- **MSE**: 331,117.44
- **RMSE**: 575.43
- **MAPE**: 15.29%

---

## Conclusion
- ARIMA performed slightly better than LSTM in this case due to the dataset's smaller size and lack of complex patterns requiring deep learning.
- Future steps include implementing Bidirectional LSTM and exploring additional hyperparameter tuning to improve deep learning model performance.

---

---
