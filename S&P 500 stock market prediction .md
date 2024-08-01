```python
import yfinance as yf
import pandas as pd
import os
```


```python
if os.path.exists("sp500.csv"):
    sp500 = pd.read_csv("sp500.csv", index_col=0)
else:
    sp500 = yf.Ticker("^GSPC")
    sp500 = sp500.history(period="max")
    sp500.to_csv("sp500.csv")
```


```python
#sp500.index = pd.to_datetime(sp500.index)
```


```python
sp500
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Dividends</th>
      <th>Stock Splits</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2024-07-26 00:00:00-04:00</th>
      <td>5433.669922</td>
      <td>5488.319824</td>
      <td>5430.700195</td>
      <td>5459.100098</td>
      <td>3638770000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-29 00:00:00-04:00</th>
      <td>5476.549805</td>
      <td>5487.740234</td>
      <td>5444.439941</td>
      <td>5463.540039</td>
      <td>3379970000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-30 00:00:00-04:00</th>
      <td>5478.729980</td>
      <td>5489.459961</td>
      <td>5401.700195</td>
      <td>5436.439941</td>
      <td>3777740000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-31 00:00:00-04:00</th>
      <td>5505.589844</td>
      <td>5551.509766</td>
      <td>5493.750000</td>
      <td>5522.299805</td>
      <td>4546910000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-08-01 00:00:00-04:00</th>
      <td>5537.839844</td>
      <td>5566.160156</td>
      <td>5457.759766</td>
      <td>5470.839844</td>
      <td>1262114000</td>
      <td>0.0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>24262 rows × 7 columns</p>
</div>




```python
sp500.index
```




    Index(['1927-12-30 00:00:00-05:00', '1928-01-03 00:00:00-05:00',
           '1928-01-04 00:00:00-05:00', '1928-01-05 00:00:00-05:00',
           '1928-01-06 00:00:00-05:00', '1928-01-09 00:00:00-05:00',
           '1928-01-10 00:00:00-05:00', '1928-01-11 00:00:00-05:00',
           '1928-01-12 00:00:00-05:00', '1928-01-13 00:00:00-05:00',
           ...
           '2024-07-19 00:00:00-04:00', '2024-07-22 00:00:00-04:00',
           '2024-07-23 00:00:00-04:00', '2024-07-24 00:00:00-04:00',
           '2024-07-25 00:00:00-04:00', '2024-07-26 00:00:00-04:00',
           '2024-07-29 00:00:00-04:00', '2024-07-30 00:00:00-04:00',
           '2024-07-31 00:00:00-04:00', '2024-08-01 00:00:00-04:00'],
          dtype='object', name='Date', length=24262)




```python
sp500.plot.line(y="Close", use_index=True)
```




    <Axes: xlabel='Date'>




    
![png](output_5_1.png)
    



```python
del sp500["Dividends"]
del sp500["Stock Splits"]
```


```python
sp500["Tomorrow"] = sp500["Close"].shift(-1)
```


```python
sp500
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.760000</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
      <td>17.719999</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
      <td>17.549999</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
      <td>17.660000</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.500000</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2024-07-26 00:00:00-04:00</th>
      <td>5433.669922</td>
      <td>5488.319824</td>
      <td>5430.700195</td>
      <td>5459.100098</td>
      <td>3638770000</td>
      <td>5463.540039</td>
    </tr>
    <tr>
      <th>2024-07-29 00:00:00-04:00</th>
      <td>5476.549805</td>
      <td>5487.740234</td>
      <td>5444.439941</td>
      <td>5463.540039</td>
      <td>3379970000</td>
      <td>5436.439941</td>
    </tr>
    <tr>
      <th>2024-07-30 00:00:00-04:00</th>
      <td>5478.729980</td>
      <td>5489.459961</td>
      <td>5401.700195</td>
      <td>5436.439941</td>
      <td>3777740000</td>
      <td>5522.299805</td>
    </tr>
    <tr>
      <th>2024-07-31 00:00:00-04:00</th>
      <td>5505.589844</td>
      <td>5551.509766</td>
      <td>5493.750000</td>
      <td>5522.299805</td>
      <td>4546910000</td>
      <td>5470.839844</td>
    </tr>
    <tr>
      <th>2024-08-01 00:00:00-04:00</th>
      <td>5537.839844</td>
      <td>5566.160156</td>
      <td>5457.759766</td>
      <td>5470.839844</td>
      <td>1262114000</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
<p>24262 rows × 6 columns</p>
</div>




```python
sp500["Target"] = (sp500["Tomorrow"] > sp500["Close"]).astype(int)
```


```python
sp500
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
      <th>Target</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1927-12-30 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.760000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1928-01-03 00:00:00-05:00</th>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>17.760000</td>
      <td>0</td>
      <td>17.719999</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-04 00:00:00-05:00</th>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>17.719999</td>
      <td>0</td>
      <td>17.549999</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1928-01-05 00:00:00-05:00</th>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>17.549999</td>
      <td>0</td>
      <td>17.660000</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1928-01-06 00:00:00-05:00</th>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>17.660000</td>
      <td>0</td>
      <td>17.500000</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2024-07-26 00:00:00-04:00</th>
      <td>5433.669922</td>
      <td>5488.319824</td>
      <td>5430.700195</td>
      <td>5459.100098</td>
      <td>3638770000</td>
      <td>5463.540039</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2024-07-29 00:00:00-04:00</th>
      <td>5476.549805</td>
      <td>5487.740234</td>
      <td>5444.439941</td>
      <td>5463.540039</td>
      <td>3379970000</td>
      <td>5436.439941</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2024-07-30 00:00:00-04:00</th>
      <td>5478.729980</td>
      <td>5489.459961</td>
      <td>5401.700195</td>
      <td>5436.439941</td>
      <td>3777740000</td>
      <td>5522.299805</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2024-07-31 00:00:00-04:00</th>
      <td>5505.589844</td>
      <td>5551.509766</td>
      <td>5493.750000</td>
      <td>5522.299805</td>
      <td>4546910000</td>
      <td>5470.839844</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2024-08-01 00:00:00-04:00</th>
      <td>5537.839844</td>
      <td>5566.160156</td>
      <td>5457.759766</td>
      <td>5470.839844</td>
      <td>1262114000</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>24262 rows × 7 columns</p>
</div>




```python
sp500 = sp500.loc["1990-01-01":].copy()
```


```python
sp500
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
      <th>Target</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1990-01-02 00:00:00-05:00</th>
      <td>353.399994</td>
      <td>359.690002</td>
      <td>351.980011</td>
      <td>359.690002</td>
      <td>162070000</td>
      <td>358.760010</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1990-01-03 00:00:00-05:00</th>
      <td>359.690002</td>
      <td>360.589996</td>
      <td>357.890015</td>
      <td>358.760010</td>
      <td>192330000</td>
      <td>355.670013</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1990-01-04 00:00:00-05:00</th>
      <td>358.760010</td>
      <td>358.760010</td>
      <td>352.890015</td>
      <td>355.670013</td>
      <td>177000000</td>
      <td>352.200012</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1990-01-05 00:00:00-05:00</th>
      <td>355.670013</td>
      <td>355.670013</td>
      <td>351.350006</td>
      <td>352.200012</td>
      <td>158530000</td>
      <td>353.790009</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1990-01-08 00:00:00-05:00</th>
      <td>352.200012</td>
      <td>354.239990</td>
      <td>350.540009</td>
      <td>353.790009</td>
      <td>140110000</td>
      <td>349.619995</td>
      <td>0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2024-07-26 00:00:00-04:00</th>
      <td>5433.669922</td>
      <td>5488.319824</td>
      <td>5430.700195</td>
      <td>5459.100098</td>
      <td>3638770000</td>
      <td>5463.540039</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2024-07-29 00:00:00-04:00</th>
      <td>5476.549805</td>
      <td>5487.740234</td>
      <td>5444.439941</td>
      <td>5463.540039</td>
      <td>3379970000</td>
      <td>5436.439941</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2024-07-30 00:00:00-04:00</th>
      <td>5478.729980</td>
      <td>5489.459961</td>
      <td>5401.700195</td>
      <td>5436.439941</td>
      <td>3777740000</td>
      <td>5522.299805</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2024-07-31 00:00:00-04:00</th>
      <td>5505.589844</td>
      <td>5551.509766</td>
      <td>5493.750000</td>
      <td>5522.299805</td>
      <td>4546910000</td>
      <td>5470.839844</td>
      <td>0</td>
    </tr>
    <tr>
      <th>2024-08-01 00:00:00-04:00</th>
      <td>5537.839844</td>
      <td>5566.160156</td>
      <td>5457.759766</td>
      <td>5470.839844</td>
      <td>1262114000</td>
      <td>NaN</td>
      <td>0</td>
    </tr>
  </tbody>
</table>
<p>8712 rows × 7 columns</p>
</div>




```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(n_estimators=100, min_samples_split=100, random_state=1)

train = sp500.iloc[:-100]
test = sp500.iloc[-100:]

predictors = ["Close", "Volume", "Open", "High", "Low"]
model.fit(train[predictors], train["Target"]) # based on input features(colums of predictors on training set), 
# it predicts target variable on training set -> the model will return predictions for target var
```




<style>#sk-container-id-1 {color: black;}#sk-container-id-1 pre{padding: 0;}#sk-container-id-1 div.sk-toggleable {background-color: white;}#sk-container-id-1 label.sk-toggleable__label {cursor: pointer;display: block;width: 100%;margin-bottom: 0;padding: 0.3em;box-sizing: border-box;text-align: center;}#sk-container-id-1 label.sk-toggleable__label-arrow:before {content: "▸";float: left;margin-right: 0.25em;color: #696969;}#sk-container-id-1 label.sk-toggleable__label-arrow:hover:before {color: black;}#sk-container-id-1 div.sk-estimator:hover label.sk-toggleable__label-arrow:before {color: black;}#sk-container-id-1 div.sk-toggleable__content {max-height: 0;max-width: 0;overflow: hidden;text-align: left;background-color: #f0f8ff;}#sk-container-id-1 div.sk-toggleable__content pre {margin: 0.2em;color: black;border-radius: 0.25em;background-color: #f0f8ff;}#sk-container-id-1 input.sk-toggleable__control:checked~div.sk-toggleable__content {max-height: 200px;max-width: 100%;overflow: auto;}#sk-container-id-1 input.sk-toggleable__control:checked~label.sk-toggleable__label-arrow:before {content: "▾";}#sk-container-id-1 div.sk-estimator input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-1 div.sk-label input.sk-toggleable__control:checked~label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-1 input.sk-hidden--visually {border: 0;clip: rect(1px 1px 1px 1px);clip: rect(1px, 1px, 1px, 1px);height: 1px;margin: -1px;overflow: hidden;padding: 0;position: absolute;width: 1px;}#sk-container-id-1 div.sk-estimator {font-family: monospace;background-color: #f0f8ff;border: 1px dotted black;border-radius: 0.25em;box-sizing: border-box;margin-bottom: 0.5em;}#sk-container-id-1 div.sk-estimator:hover {background-color: #d4ebff;}#sk-container-id-1 div.sk-parallel-item::after {content: "";width: 100%;border-bottom: 1px solid gray;flex-grow: 1;}#sk-container-id-1 div.sk-label:hover label.sk-toggleable__label {background-color: #d4ebff;}#sk-container-id-1 div.sk-serial::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: 0;}#sk-container-id-1 div.sk-serial {display: flex;flex-direction: column;align-items: center;background-color: white;padding-right: 0.2em;padding-left: 0.2em;position: relative;}#sk-container-id-1 div.sk-item {position: relative;z-index: 1;}#sk-container-id-1 div.sk-parallel {display: flex;align-items: stretch;justify-content: center;background-color: white;position: relative;}#sk-container-id-1 div.sk-item::before, #sk-container-id-1 div.sk-parallel-item::before {content: "";position: absolute;border-left: 1px solid gray;box-sizing: border-box;top: 0;bottom: 0;left: 50%;z-index: -1;}#sk-container-id-1 div.sk-parallel-item {display: flex;flex-direction: column;z-index: 1;position: relative;background-color: white;}#sk-container-id-1 div.sk-parallel-item:first-child::after {align-self: flex-end;width: 50%;}#sk-container-id-1 div.sk-parallel-item:last-child::after {align-self: flex-start;width: 50%;}#sk-container-id-1 div.sk-parallel-item:only-child::after {width: 0;}#sk-container-id-1 div.sk-dashed-wrapped {border: 1px dashed gray;margin: 0 0.4em 0.5em 0.4em;box-sizing: border-box;padding-bottom: 0.4em;background-color: white;}#sk-container-id-1 div.sk-label label {font-family: monospace;font-weight: bold;display: inline-block;line-height: 1.2em;}#sk-container-id-1 div.sk-label-container {text-align: center;}#sk-container-id-1 div.sk-container {/* jupyter's `normalize.less` sets `[hidden] { display: none; }` but bootstrap.min.css set `[hidden] { display: none !important; }` so we also need the `!important` here to be able to override the default hidden behavior on the sphinx rendered scikit-learn.org. See: https://github.com/scikit-learn/scikit-learn/issues/21755 */display: inline-block !important;position: relative;}#sk-container-id-1 div.sk-text-repr-fallback {display: none;}</style><div id="sk-container-id-1" class="sk-top-container"><div class="sk-text-repr-fallback"><pre>RandomForestClassifier(min_samples_split=100, random_state=1)</pre><b>In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook. <br />On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.</b></div><div class="sk-container" hidden><div class="sk-item"><div class="sk-estimator sk-toggleable"><input class="sk-toggleable__control sk-hidden--visually" id="sk-estimator-id-1" type="checkbox" checked><label for="sk-estimator-id-1" class="sk-toggleable__label sk-toggleable__label-arrow">RandomForestClassifier</label><div class="sk-toggleable__content"><pre>RandomForestClassifier(min_samples_split=100, random_state=1)</pre></div></div></div></div></div>




```python
from sklearn.metrics import precision_score

preds = model.predict(test[predictors])  
#returns a new array that contain predictions(predicted values) for the target variable in test set
```


```python
preds = pd.Series(preds, index=test.index) # pandas.Series : a single column of data with an associated index
```


```python
precision_score(test["Target"], preds) # compare the actual target value and predicted values from test set
# precision score = TP/ (TP + FP) -> what fraction actually matches to true target value?
```




    0.5454545454545454




```python
combined = pd.concat([test["Target"], preds], axis=1) # rows (axis=0) or columns (axis=1)
```


```python
combined.plot()
```




    <Axes: xlabel='Date'>




    
![png](output_18_1.png)
    



```python
def predict(train, test, predictors, model):
    model.fit(train[predictors], train["Target"])
    preds = model.predict(test[predictors])
    preds = pd.Series(preds, index=test.index, name="Predictions")
    combined = pd.concat([test["Target"], preds], axis=1)
    return combined
```


```python
def backtest(data, model, predictors, start=2500, step=250):
    all_predictions = []
    
    for i in range(start, data.shape[0], step):
        train = data.iloc[0:i].copy()
        test = data.iloc[i:(i+step)].copy()
        predictions = predict(train, test, predictors, model)
        all_predictions.append(predictions)
    return pd.concat(all_predictions)
```


```python
predictions = backtest(sp500, model, predictors)
```


```python
predictions["Predictions"].value_counts() #counts the occurrences of each value in Predictions column (0 and 1)
```




    0    3616
    1    2596
    Name: Predictions, dtype: int64




```python
precision_score(predictions["Target"], predictions["Predictions"])
```




    0.5288906009244992




```python
predictions["Target"].value_counts() / predictions.shape[0] 
# gives out relative frequency of each value (0, 1) in Target Column in predictions
```




    1    0.535254
    0    0.464746
    Name: Target, dtype: float64




```python
horizons = [2,5,60,250,1000] # different time horizons(in trading )
new_predictors = []

for horizon in horizons:
    rolling_averages = sp500.rolling(horizon).mean() # horizon represents the window size
    # As the window moves forward, it includes the next data point and excludes the first one from the previous window
    
    ratio_column = f"Close_Ratio_{horizon}"
    sp500[ratio_column] = sp500["Close"] / rolling_averages["Close"]
    
    trend_column = f"Trend_{horizon}"
    sp500[trend_column] = sp500.shift(1).rolling(horizon).sum()["Target"] 
    # trend column cannot include the current day
    # to look the past data only (historical data trend)
    new_predictors += [ratio_column, trend_column]
```


```python
sp500 = sp500.dropna()
```


```python
sp500
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Open</th>
      <th>High</th>
      <th>Low</th>
      <th>Close</th>
      <th>Volume</th>
      <th>Tomorrow</th>
      <th>Target</th>
      <th>Close_Ratio_2</th>
      <th>Trend_2</th>
      <th>Close_Ratio_5</th>
      <th>Trend_5</th>
      <th>Close_Ratio_60</th>
      <th>Trend_60</th>
      <th>Close_Ratio_250</th>
      <th>Trend_250</th>
      <th>Close_Ratio_1000</th>
      <th>Trend_1000</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1993-12-14 00:00:00-05:00</th>
      <td>465.730011</td>
      <td>466.119995</td>
      <td>462.459991</td>
      <td>463.059998</td>
      <td>275050000</td>
      <td>461.839996</td>
      <td>0</td>
      <td>0.997157</td>
      <td>1.0</td>
      <td>0.996617</td>
      <td>1.0</td>
      <td>1.000283</td>
      <td>32.0</td>
      <td>1.028047</td>
      <td>127.0</td>
      <td>1.176082</td>
      <td>512.0</td>
    </tr>
    <tr>
      <th>1993-12-15 00:00:00-05:00</th>
      <td>463.059998</td>
      <td>463.690002</td>
      <td>461.839996</td>
      <td>461.839996</td>
      <td>331770000</td>
      <td>463.339996</td>
      <td>1</td>
      <td>0.998681</td>
      <td>0.0</td>
      <td>0.995899</td>
      <td>1.0</td>
      <td>0.997329</td>
      <td>32.0</td>
      <td>1.025151</td>
      <td>126.0</td>
      <td>1.172676</td>
      <td>512.0</td>
    </tr>
    <tr>
      <th>1993-12-16 00:00:00-05:00</th>
      <td>461.859985</td>
      <td>463.980011</td>
      <td>461.859985</td>
      <td>463.339996</td>
      <td>284620000</td>
      <td>466.380005</td>
      <td>1</td>
      <td>1.001621</td>
      <td>1.0</td>
      <td>0.999495</td>
      <td>2.0</td>
      <td>1.000311</td>
      <td>32.0</td>
      <td>1.028274</td>
      <td>127.0</td>
      <td>1.176163</td>
      <td>513.0</td>
    </tr>
    <tr>
      <th>1993-12-17 00:00:00-05:00</th>
      <td>463.339996</td>
      <td>466.380005</td>
      <td>463.339996</td>
      <td>466.380005</td>
      <td>363750000</td>
      <td>465.850006</td>
      <td>0</td>
      <td>1.003270</td>
      <td>2.0</td>
      <td>1.004991</td>
      <td>3.0</td>
      <td>1.006561</td>
      <td>32.0</td>
      <td>1.034781</td>
      <td>128.0</td>
      <td>1.183537</td>
      <td>514.0</td>
    </tr>
    <tr>
      <th>1993-12-20 00:00:00-05:00</th>
      <td>466.380005</td>
      <td>466.899994</td>
      <td>465.529999</td>
      <td>465.850006</td>
      <td>255900000</td>
      <td>465.299988</td>
      <td>0</td>
      <td>0.999431</td>
      <td>1.0</td>
      <td>1.003784</td>
      <td>2.0</td>
      <td>1.005120</td>
      <td>32.0</td>
      <td>1.033359</td>
      <td>128.0</td>
      <td>1.181856</td>
      <td>513.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2024-07-25 00:00:00-04:00</th>
      <td>5428.700195</td>
      <td>5491.589844</td>
      <td>5390.950195</td>
      <td>5399.220215</td>
      <td>4592120000</td>
      <td>5459.100098</td>
      <td>1</td>
      <td>0.997422</td>
      <td>0.0</td>
      <td>0.983411</td>
      <td>1.0</td>
      <td>1.002786</td>
      <td>37.0</td>
      <td>1.109856</td>
      <td>140.0</td>
      <td>1.262183</td>
      <td>529.0</td>
    </tr>
    <tr>
      <th>2024-07-26 00:00:00-04:00</th>
      <td>5433.669922</td>
      <td>5488.319824</td>
      <td>5430.700195</td>
      <td>5459.100098</td>
      <td>3638770000</td>
      <td>5463.540039</td>
      <td>1</td>
      <td>1.005515</td>
      <td>1.0</td>
      <td>0.995983</td>
      <td>2.0</td>
      <td>1.012581</td>
      <td>38.0</td>
      <td>1.121356</td>
      <td>140.0</td>
      <td>1.275539</td>
      <td>529.0</td>
    </tr>
    <tr>
      <th>2024-07-29 00:00:00-04:00</th>
      <td>5476.549805</td>
      <td>5487.740234</td>
      <td>5444.439941</td>
      <td>5463.540039</td>
      <td>3379970000</td>
      <td>5436.439941</td>
      <td>0</td>
      <td>1.000406</td>
      <td>2.0</td>
      <td>1.000475</td>
      <td>2.0</td>
      <td>1.012012</td>
      <td>39.0</td>
      <td>1.121462</td>
      <td>140.0</td>
      <td>1.275940</td>
      <td>529.0</td>
    </tr>
    <tr>
      <th>2024-07-30 00:00:00-04:00</th>
      <td>5478.729980</td>
      <td>5489.459961</td>
      <td>5401.700195</td>
      <td>5436.439941</td>
      <td>3777740000</td>
      <td>5522.299805</td>
      <td>1</td>
      <td>0.997514</td>
      <td>1.0</td>
      <td>0.999881</td>
      <td>2.0</td>
      <td>1.005836</td>
      <td>38.0</td>
      <td>1.115112</td>
      <td>140.0</td>
      <td>1.268992</td>
      <td>528.0</td>
    </tr>
    <tr>
      <th>2024-07-31 00:00:00-04:00</th>
      <td>5505.589844</td>
      <td>5551.509766</td>
      <td>5493.750000</td>
      <td>5522.299805</td>
      <td>4546910000</td>
      <td>5470.839844</td>
      <td>0</td>
      <td>1.007835</td>
      <td>1.0</td>
      <td>1.012129</td>
      <td>3.0</td>
      <td>1.020480</td>
      <td>38.0</td>
      <td>1.131787</td>
      <td>141.0</td>
      <td>1.288381</td>
      <td>528.0</td>
    </tr>
  </tbody>
</table>
<p>7711 rows × 17 columns</p>
</div>




```python
model = RandomForestClassifier(n_estimators=200, min_samples_split=50, random_state =1)
```


```python
def predict(train, test, predictors, model):
    model.fit(train[predictors], train["Target"])
    preds = model.predict_proba(test[predictors])[:,1]
    # returns probability of that stock price will go up or down(instead of boolean 0,1)
    preds[preds >= .6] = 1
    preds[preds < .6] = 0 
    # threshold is changed
    # -> model should be more confident(60%) to predict a positive outcome
    # it will reduce false positives. Limitation: may increase false negatives
    preds = pd.Series(preds, index=test.index, name="Predictions")
    combined = pd.concat([test["Target"], preds], axis=1)
    return combined
```


```python
predictions = backtest(sp500, model, new_predictors)
```


```python
predictions["Predictions"].value_counts()
```




    0.0    4372
    1.0     839
    Name: Predictions, dtype: int64




```python
precision_score(predictions["Target"], predictions["Predictions"])
```




    0.5744934445768772




```python
predictions["Target"].value_counts()/predictions.shape[0]
```




    1    0.545001
    0    0.454999
    Name: Target, dtype: float64




```python
predictions
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Target</th>
      <th>Predictions</th>
    </tr>
    <tr>
      <th>Date</th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>2003-11-14 00:00:00-05:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2003-11-17 00:00:00-05:00</th>
      <td>0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>2003-11-18 00:00:00-05:00</th>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>2003-11-19 00:00:00-05:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2003-11-20 00:00:00-05:00</th>
      <td>1</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>2024-07-25 00:00:00-04:00</th>
      <td>1</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-26 00:00:00-04:00</th>
      <td>1</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-29 00:00:00-04:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-30 00:00:00-04:00</th>
      <td>1</td>
      <td>0.0</td>
    </tr>
    <tr>
      <th>2024-07-31 00:00:00-04:00</th>
      <td>0</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
<p>5211 rows × 2 columns</p>
</div>




