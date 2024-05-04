# Weather Forecast in New Delhi
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![imblearn](https://img.shields.io/badge/imblearn-green?style=for-the-badge&logo=imblearn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/matplotlib-%233A4CAA.svg?style=for-the-badge&logo=matplotlib&logoColor=white)
![Seaborn](https://img.shields.io/badge/seaborn-%2302B6D6.svg?style=for-the-badge&logo=seaborn&logoColor=white)
![Prophet](https://img.shields.io/badge/prophet-%234591A6.svg?style=for-the-badge&logo=prophet&logoColor=white)

## About

This project focuses on analyzing and forecasting weather data in New Delhi for the period spanning 2013 to 2017. The dataset contains daily weather observations recorded over this time span, and includes important meteorological features such as: <br>

Date: The date of the observation.<br>
Mean Temperature: The average temperature recorded on that day, measured in degrees Celsius.<br>
Humidity: The average humidity percentage recorded on that day.<br>
Wind Speed: The average wind speed recorded on that day, measured in meters per second.<br>
Mean Pressure: The average atmospheric pressure recorded on that day, measured in hPa (hectopascals).<br>
By examining these key weather attributes, this project aims to provide valuable insights into weather patterns in New Delhi over the course of five years. Moreover, the project seeks to build a predictive model that can forecast future weather conditions based on historical data.

## Dataset
Dataset: 
* Training Dataset: [Download](https://github.com/tranvietcuong03/weather_forecasting/blob/master/DailyDelhiClimateTrain.csv).
* Testing Dataset : [Download](https://github.com/tranvietcuong03/weather_forecasting/blob/master/DailyDelhiClimateTest.csv)
<br>
It will be this: <br>

|       | Date       | Mean Temp | Humidity | Wind Speed | Mean Pressure |
|-------|------------|-----------|----------|------------|---------------|
| 0     | 2013-01-01 | 10.000000 | 84.500000| 0.000000   | 1015.666667   |
| 1     | 2013-01-02 | 7.400000  | 92.000000| 2.980000   | 1017.800000   |
| 2     | 2013-01-03 | 7.166667  | 87.000000| 4.633333   | 1018.666667   |
| 3     | 2013-01-04 | 8.666667  | 71.333333| 1.233333   | 1017.166667   |
| 4     | 2013-01-05 | 6.000000  | 86.833333| 3.700000   | 1016.500000   |


## Analyzing:
* Look at the descriptive statistics of the data: <br>

| Statistic | Meantemp   | Humidity | Wind Speed | Mean Pressure |
|-----------|------------|----------|------------|---------------|
| Count     | 1462.000000 | 1462.000000 | 1462.000000 | 1462.000000 |
| Mean      | 25.495521   | 60.771702  | 6.802209   | 1011.104548 |
| Std Dev   | 7.348103    | 16.769652  | 4.561602   | 180.231668  |
| Min       | 6.000000    | 13.428571  | 0.000000   | -3.041667  |
| 25th %ile | 18.857143   | 50.375000  | 3.475000   | 1001.580357 |
| Median    | 27.714286   | 62.625000  | 6.221667   | 1008.563492 |
| 75th %ile | 31.305804   | 72.218750  | 9.238235   | 1014.944901 |
| Max       | 38.714286   | 100.000000 | 42.220000  | 7679.333333 |

<br>
* Look at the temperature change in Delhi over the years:
![...](https://github.com/tranvietcuong03/weather_forecasting/blob/master/analyze_temperature.png)

## Setup
- Requirement: Ensure you have Python 3 and required libraries installed (pandas, numpy, sklearn, matplotlib, seaborn, prophet).
- Installation:
  * Pandas
  ```sh
  pip install pandas
  ```
   * Prophet (Facebook model):
  ```sh
  pip install prophet
  ```
  There are similar to numpy, scikit-learn, matplotlib and seaborn to install
  
## Model
The Facebook prophet model is one of the best techniques for time series forecasting. The prophet model accepts time data named as “ds”, and labels as “y”. Therefore, i convert the data into this format:
|     | ds         | y        | Humidity | Wind Speed | Mean Pressure | Year | Month |
|-----|------------|----------|----------|------------|---------------|------|-------|
| 0   | 2013-01-01 | 10.000000 | 84.500000 | 0.000000  | 1015.666667 | 2013 | 1     |
| 1   | 2013-01-02 | 7.400000  | 92.000000 | 2.980000  | 1017.800000 | 2013 | 1     |
| 2   | 2013-01-03 | 7.166667  | 87.000000 | 4.633333  | 1018.666667 | 2013 | 1     |
| 3   | 2013-01-04 | 8.666667  | 71.333333 | 1.233333  | 1017.166667 | 2013 | 1     |
| 4   | 2013-01-05 | 6.000000  | 86.833333 | 3.700000  | 1016.500000 | 2013 | 1     |
| ... | ...        | ...      | ...      | ...        | ...         | ...  | ...   |

<br>
Forecast the weather using the Facebook prophet model:
![...](https://github.com/tranvietcuong03/weather_forecasting/blob/master/weather_forecasting.png).

## Result:
Functions model i have the prediction which compare to the actual number in the Test dataset:
* Mean Absolute Error (MAE): 2.1925
* Root Mean Squared Error (RMSE): 7.1289
* R2 Score (R2): 0.8222
