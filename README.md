# S&P500 stock market prediction

## Executive Summary:
Using JupyterLab, Python 3.9+, and Python packages(pandas, yfinance, scikit-learn), I developed a machine learning model for predicting stock price movements. 

The project progressed through the following key stages:

1. Created an initial machine learning model to estimate accuracy.
2. Built a backtesting engine for a more accurate accuracy estimate.
3. Implemented rolling averages to improve the model's accuracy.

## Methodology

1. **Data Acquisition**:
   - Downloaded S&P 500 historical data using yfinance
   - Stored data in a CSV file for efficient access

2. **Data Preprocessing**:

   - Cleaned and prepared data using pandas
   - Created new features like "Tomorrow" price and "Target" (binary indicator for price increase)

3. **Model Development**:

   - Used RandomForestClassifier from scikit-learn
   - Trained on historical data excluding the most recent 100 days

4. **Backtesting**:

   - Developed a custom backtesting function to simulate real-world trading scenarios
   - Used a sliding window approach to test the model on different time periods

5. **Model Evaluation**:

   - Utilized precision score as the primary metric for model performance

## Code
The main prediction model can be found in our [prediction script](S&P 500 stock market prediction.py). 

## Data
Downloades all of the data during the project, using the -yfinance package.

