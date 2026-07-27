# Using Machine Learning to Develop Stock Projections for BTC-USD

## Project Overview

This project focuses on developing predictive models to forecast Bitcoin (BTC/USD) price movements using historical cryptocurrency data and time-series analysis techniques.

The project began by addressing challenges in collecting and processing BTC/USD market data from Yahoo Finance. After resolving data extraction, formatting, and preprocessing issues, multiple forecasting models were implemented and evaluated to determine their ability to predict future Bitcoin price trends.

The final project compares three statistical forecasting approaches:

- ARMA (AutoRegressive Moving Average)
- ARIMA (AutoRegressive Integrated Moving Average)
- SARIMAX (Seasonal AutoRegressive Integrated Moving Average with Exogenous Variables)

The goal of this project was to explore how machine learning and statistical modeling techniques can be applied to financial time-series data to identify patterns and generate future price projections.

---

# Objectives and Goals

The main objectives of this project were:

- Collect and preprocess historical BTC/USD price data
- Develop a reliable pipeline for analyzing cryptocurrency market trends
- Apply time-series forecasting techniques to predict future Bitcoin prices
- Compare multiple forecasting models and evaluate their performance
- Visualize predicted prices against actual market behavior
- Analyze the strengths and limitations of traditional forecasting methods for volatile financial markets

---

# Methodology

## Data Collection and Preprocessing

The initial phase of the project involved extracting BTC/USD historical price data from Yahoo Finance.

Several challenges were encountered during the data collection process, including:

- Changes in Yahoo Finance's response format
- Encrypted data returned by updated versions of `pandas_datareader`
- Missing dependencies and compatibility issues between Python libraries
- Incorrect CSV formatting and column ordering
- Date conversion and indexing errors

To resolve these issues:

- A custom CSV reading function was developed to process historical BTC/USD data
- The dataset was reformatted into a Pandas DataFrame
- Date values were converted into appropriate time-series indices
- Column ordering was corrected to ensure compatibility with the forecasting pipeline
- Training and testing datasets were properly separated

The final dataset consisted of BTC/USD historical prices from:

**Training Period:** January 1, 2018 – October 31, 2020  
**Testing Period:** November 1, 2020 – December 2, 2020

The adjusted closing price was used as the primary forecasting variable.

---

# Forecasting Models

## ARMA Model

The first forecasting approach implemented was the **AutoRegressive Moving Average (ARMA)** model.

ARMA combines:

- **Autoregression (AR):** Uses previous price values to predict future values
- **Moving Average (MA):** Uses previous prediction errors to improve future forecasts

Implementation:

```python
SARIMAX(y, order=(1,0,1))
```

The model was trained using historical BTC/USD prices and used to forecast future price movements.

---

## ARIMA Model

The **AutoRegressive Integrated Moving Average (ARIMA)** model was implemented to better handle non-stationary financial data.

ARIMA extends ARMA by adding:

- Differencing to remove trends and stabilize the dataset
- Improved ability to model changing price patterns

Different parameter configurations were tested, including:

```python
ARIMA(y, order=(2,2,2))
```

and:

```python
ARIMA(y, order=(5,4,2))
```

The model was evaluated based on its ability to capture Bitcoin price trends and changing market behavior.

---

## SARIMAX Model

The final model implemented was **Seasonal ARIMA with Exogenous Variables (SARIMAX)**.

SARIMAX extends ARIMA by incorporating seasonal patterns, allowing the model to capture recurring trends within time-series data.

Implementation:

```python
SARIMAX(
    y,
    order=(5,4,2),
    seasonal_order=(2,2,2,12)
)
```

Due to its increased complexity, SARIMAX required additional processing time compared to the other models.

---

# Model Evaluation

Each forecasting model was evaluated using **Root Mean Squared Error (RMSE)**:

\[
RMSE = \sqrt{\frac{1}{n}\sum(y_i-\hat{y_i})^2}
\]

RMSE measures the difference between predicted and actual Bitcoin prices. Lower values indicate predictions that are closer to observed market values.

The models were compared based on:

- Prediction accuracy
- Ability to follow historical price trends
- Consistency between visual results and calculated performance metrics

---

# Results and Key Findings

The project successfully developed and evaluated three BTC/USD forecasting models: ARMA, ARIMA, and SARIMAX.

## Data Pipeline Improvements

A major finding from this project was that accurate forecasting depends heavily on reliable data preparation.

Initial model predictions were inaccurate due to:

- Incorrect dataset ranges
- Improper training/testing separation
- CSV column ordering issues
- Date formatting inconsistencies

After correcting these issues, model predictions became more aligned with actual BTC/USD price trends.

---

## ARMA Results

The ARMA model successfully generated Bitcoin price forecasts based on historical trends.

Key observations:

- The model captured short-term relationships in historical prices
- Predictions initially underestimated Bitcoin's upward movement
- Performance was limited when handling large market fluctuations

---

## ARIMA Results

The ARIMA model improved upon ARMA by incorporating differencing to handle non-stationary data.

Key observations:

- Multiple parameter configurations were tested
- Higher differencing values helped capture larger price movements
- Some early predictions appeared visually accurate but produced inconsistent RMSE values due to preprocessing issues
- After correcting data handling problems, ARIMA predictions better reflected market trends

---

## SARIMAX Results

The SARIMAX model provided a more advanced forecasting approach by incorporating seasonal patterns.

Key observations:

- The model required significantly more processing time due to increased complexity
- Initial performance metrics were inaccurate because of incorrect training/testing boundaries
- After debugging the dataset pipeline, SARIMAX produced more meaningful forecasts

# Results and Key Findings

The project successfully developed and evaluated three BTC/USD forecasting models: ARMA, ARIMA, and SARIMAX. Model performance was evaluated using Root Mean Squared Error (RMSE), where lower values indicate predictions closer to the actual Bitcoin price.

## Model Performance

| Model | Parameters | RMSE | Key Findings |
|------|------------|------|--------------|
| ARMA | (1,0,1) | 3646.75 | Captured short-term price patterns but struggled with large market movements |
| ARIMA | (5,4,2) | 897.56 | Produced the lowest RMSE and best overall predictive accuracy |
| SARIMAX | (5,4,2), Seasonal (2,2,2,12) | 913.42 | Performed similarly to ARIMA while incorporating seasonal patterns |

---

## ARMA Results

The ARMA model was implemented using:

```python
SARIMAX(y, order=(1,0,1))
```

---

## Overall Findings

The project demonstrated that time-series forecasting models can identify patterns within historical cryptocurrency data; however, accurately predicting Bitcoin prices remains challenging due to market volatility and unpredictable external factors.

The largest improvements came from:

- Correct data preprocessing
- Proper dataset segmentation
- Careful model parameter selection
- Validation of predictions against actual market behavior

This project highlighted the importance of both machine learning techniques and robust data engineering practices when developing predictive models.

---

# Visualizations

The project generates visual comparisons between actual Bitcoin prices and model predictions.

Visualizations include:

- Historical BTC/USD price trends
- Training and testing dataset split
- ARMA predictions
- ARIMA predictions
- SARIMAX predictions

<img width="767" height="437" alt="image" src="https://github.com/user-attachments/assets/7dceeb26-e877-497c-8f11-1cf5178a920a" />


The graphs allow comparison between predicted values and actual BTC/USD market movements.

---

# Potential Next Steps

Future improvements could include:

## Feature Engineering

Adding additional market indicators:

- Trading volume
- Moving averages
- Price volatility
- Market momentum indicators
- Technical analysis features

## Advanced Machine Learning Models

Exploring modern predictive approaches:

- Long Short-Term Memory Networks (LSTM)
- Recurrent Neural Networks (RNN)
- Transformer-based forecasting models
- Ensemble learning methods

## Model Optimization

Potential improvements:

- Automated hyperparameter tuning
- Time-series cross-validation
- Larger historical datasets
- Real-time cryptocurrency data integration

## Deployment

Potential applications:

- Interactive BTC/USD forecasting dashboard
- Real-time prediction API
- Cryptocurrency market analysis platform

---

# Individual Contributions

**Nicole Adelson**

- Developed the BTC/USD forecasting pipeline
- Debugged Yahoo Finance data extraction issues
- Created a custom CSV data processing workflow
- Cleaned and formatted historical cryptocurrency data
- Implemented ARMA, ARIMA, and SARIMAX forecasting models
- Split data into training and testing datasets
- Evaluated models using RMSE
- Generated prediction visualizations
- Analyzed model performance and identified future improvements

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Statsmodels
- Scikit-learn
- Jupyter Notebook

---

# Author

**Nicole Adelson**  
Computer Engineering Student | AI & Machine Learning Enthusiast
