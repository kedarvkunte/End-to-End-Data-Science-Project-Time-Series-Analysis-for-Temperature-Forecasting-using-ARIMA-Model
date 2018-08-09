

## Requirements

* Python 3.5 or higher
* Numpy
* Pandas
* Matplotlib
* Statsmodels

## Dataset

In this project, the Dataset used is the famous Kaggle [Dataset](https://www.kaggle.com/berkeleyearth/climate-change-earth-surface-temperature-data).

## Exploratory Data Analysis

First we use pandas to read the CSV file. After that we perform Data Cleaning such as removing unwanted columns, identifying and filling the missing values.

##  Checking Time Series Data Stationarity:

This is achieved using Augmented Dickey-Fuller test which assists finding out the stationary properties in the Time series data.

The stationarity check is carried out using the plot and p-value is tested.

![Stationary_Check](https://github.com/kedarvkunte/Time-Series-Analysis-for-Temperature-Forecasting-using-ARIMA-Model/blob/master/Rolling%20Mean.png)

### Augmented Dickey-Fuller test:
type of df_test:  <class 'tuple'>\
df_test: (-4.271198430066125, 0.00049808780753740904, 16, 508, {'1%': -3.4432882895877501, '10%': -2.5698092313534628, '5%': -2.8672462791357867}, 2060.5638228165117)\
df_output: \
 Test Statistic                  -4.271198\
#### p-value                          0.000498\
#Lags Used                      16.000000\
Number of Observations Used    508.000000\
dtype: float64\
Test Statistic                  -4.271198\
p-value                          0.000498\
#Lags Used                      16.000000\
Number of Observations Used    508.000000\
Critical Value (1%)             -3.443288\
Critical Value (10%)            -2.569809\
Critical Value (5%)             -2.867246\
dtype: float64\


As the p-value is below the threshold value, thus we can reject null-hypothesis which states that the data is not stationary.

## Modelling and Forecasting Temperature

I used ARIMA model which stands for "Auto-Regressive Integrated Moving Averages".

In this case as the data is stationary therefore only AR and MA have been taken into account.

Then AIC is calculated and then I found values of p and q having lowest AIC where the p represents the number of Auto-Regressive (AR) terms and q represents the number of Moving Averages (MA) terms.

After that the results are predicted. Here is the example of results. 



| Year  | Temperature Forecasting |
| :---: | :---: |
|2023-01-01 | -0.244643 |
|2023-02-01 |  0.817309 |
|2023-03-01 |  4.039086 |
|2023-04-01 |  8.557097 |
|2023-05-01 | 13.160331 |
|2023-06-01 | 16.614962 |
|2023-07-01 | 17.995051 |
|2023-08-01 | 16.930731 |
|2023-09-01 | 13.707325 |
|2023-10-01 |  9.188862 |
|2023-11-01 |  4.586472 |
|2023-12-01 |  1.133756 |

