# BTC/USD Price Projections

A time-series forecasting project that predicts Bitcoin (BTC/USD) price movements using statistical modeling techniques.

## Overview

This project explores the use of time-series analysis to forecast Bitcoin prices based on historical market data. Multiple forecasting models are trained and compared to evaluate their ability to predict future BTC/USD price trends.

The implemented models include:

- ARMA (AutoRegressive Moving Average)
- ARIMA (AutoRegressive Integrated Moving Average)
- SARIMAX (Seasonal AutoRegressive Integrated Moving Average)

## Project Goals

- Analyze historical Bitcoin price trends
- Apply time-series forecasting techniques
- Compare model performance using prediction accuracy metrics
- Visualize predicted vs. actual market prices

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- Scikit-learn

## Dataset

Historical BTC/USD price data was used for training and evaluation.

**Training Data:**  
January 2018 - October 2020

**Testing Data:**  
November 2020 - December 2020

The models use Bitcoin adjusted closing prices to generate future projections.

## Models

### ARMA
Captures relationships between past price values and forecast errors to model short-term trends.

### ARIMA
Uses differencing and autoregressive patterns to handle non-stationary financial data.

### SARIMAX
Extends ARIMA by incorporating seasonal patterns to improve forecasting performance.

## Results

Each model generates BTC/USD price predictions that are compared against actual market values.

Performance is evaluated using **Root Mean Squared Error (RMSE)**, where lower values indicate better predictive accuracy.

The project outputs:

- Training and testing data comparisons
- Forecasted BTC/USD prices
- Model performance metrics

## Future Improvements

- Incorporate additional market indicators such as trading volume and volatility
- Experiment with machine learning and deep learning approaches (LSTM, Transformers)
- Perform automated hyperparameter tuning
- Build an interactive dashboard for real-time predictions

## Author

**Nicole Adelson**  
Computer Engineering Student | AI & Machine Learning Enthusiast
