## Forecast the Sold-Out Date of Sporting Goods


## Task Description
Use the sales data from a period of four months to develop a prediction model, which can be used to predict the products time of sell out in the following month. The aim is to predict as accurately as possible the precise day when items will sell out.

## Dataset
Provided by Data Mining Cup 2018 (International Student Competition)
https://www.data-mining-cup.com/reviews/dmc-2018/

## Solution
**Step 1**: Data exploration and cleaning
- time searies
- outlier detection
- statistical data

**Step 2**: Feature Engineering
- create new features based on historical sales and stock data
- create lag features
- involve reasonable external features. e.g. Sepcial brand group, weather
- feature selection

**Step 3**: Clustering
- sales tendency shows 'grouping' pattern, so we decide to apply cluster before time-series model
- try 'hard' clustering by data category and ML clustering models

**Step 4**: Time-Series Model
- pure time-series model: ARIMA
- to involve more features duting prediction, also used tree-based regressions

**Step 5**: Model Ensembling
- method 1: combine best model from different clusters
- method 2: stacking

## Result
- Metrics: sum of absolute error dates of all 10,000 products
- Baseline: 261.02
- Our Result:

Model | Avg.Score | Standard Deviation | 
--- | --- | --- | --- |--- |
ARIMA | 248.9 | 0.34 |
Windowing-lag20 w/ ANN | 250.8 | 0,38 |
GBoost Regression | 253.6 | 0,59 |
GBR w/ sumUnits | 251.7  | 0,45 |
Combine Model | 245.8 | 0,37 |
Ensemble Model | 250.9 | 0,61  |

## Usage
This repos is used to store the code without the raw dataset. So the code is not directlly runnable with the cup data, but all intermediate results are maintained inside the jupyter notebook.
