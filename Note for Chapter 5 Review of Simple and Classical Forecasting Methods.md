## 5.1 Simple Forecasting Methods 

### 5.1.1 Forecast Performance Baseline 

- Simple
- Fast 
- Repeatable 



### 5.1.2 Forecast Strategies 

- Naive 
- Average 



### 5.1.3 Naive Forecasting Strategy 

Using the previous observation directly as the forecast without any change. It is called the persistence forecast



### 5.1.4 Average Forecast Strategy 



## 5.2 Autoregressive Methods 

### 5.2.1 Autoregressive Integrated Moving Average Model 

- AR: Autoregression
- I: Integrated 
- MA: Moving Average 



ARIMA expects data that is either not seasonal or has the seasonal component removed. 



### 5.2.2 What is Seasonal ARIMA 

Seasonal Autoregressive Integrated Moving Average. The seasonal part of the model consists of terms that are very similar to the non-seasonal components of the model, but they involve backshifts of the seasonal period.



### 5.2.3 How to configure SARIMA 

__Trend Element__ 

- p: Trend autoregression order.
- d: Trend difference order.
- q: Trend moving average order.

__Seasonal Element__

- P: Seasonal autoregressive order.
- D: Seasonal difference order.
- Q: Seasonal moving average order.
- m: The number of time steps for a single seasonal period.

SARIMA(p, d, q)(P, D, Q)m. 

m parameter influences the P, D, and Q parameters. 

ACF and PACF plots can be analyzed to specify values for the seasonal model by looking at correlation at seasonal lag time steps.

Therefore, it is appropriate to try out a wide range of models when fitting to data and choose a best fitting model using an appropriate criterion. 



### 5.2.4 Implementing ARIMA and SARIMA Models 



## 5.3 Exponential Smoothing Methods 

1. __like the Box-Jenkins ARIMA family__: prediction is a weighted linear sum of recent past observations or lags. 
2. __Exponential smoothing forecasting__:  a weighted sum of past observations, but the model explicitly uses an exponentially decreasing weight for past observations. Specifically, past observations are weighted with a geometrically decreasing ratio.



### 5.3.2 Single Exponential Smoothing 

time series forecasting method for univariate data without a trend or seasonality. It requires smoothing factor $\alpha$ . 

$\alpha\in [0, 1]$: This parameter controls the rate at which the influence of the observations at prior time steps
decay exponentially. 



### 5.3.3 Double Exponential Smoothing

In addition to the alpha parameter for controlling
smoothing factor for the level, an additional smoothing factor is added to control the decay ofthe influence of the change in trend called beta (b or $\beta$).

- Additive Trend: Double Exponential Smoothing with a linear trend.
- Multiplicative Trend: Double Exponential Smoothing with an exponential trend.

A damping coefficient Phi (p or $\phi$) is used to control the rate of dampening.

􏰀 Alpha ($\alpha$): Smoothing factor for the level.
􏰀 Beta ($\beta$): Smoothing factor for the trend.
􏰀 Trend Type: Additive or multiplicative.
􏰀 Dampen Type: Additive or multiplicative.
􏰀 Phi ($\psi$): Damping coefficient.

### 5.3.4 Triple Exponential Smoothing 

Triple Exponential Smoothing is an extension of Exponential Smoothing that explicitly adds support for seasonality to the univariate time series. a new parameter is added called gamma (g or $\gamma$) that controls the influence on the seasonal component

- 􏰀  Additive Seasonality: Triple Exponential Smoothing with a linear seasonality. 

- 􏰀  Multiplicative Seasonality: Triple Exponential Smoothing with an exponential season- 

  ality. 

the number of time steps in a seasonal period (Period) must be specified. For example, if the series was monthly data and the seasonal period repeated each year, then the Period=12.  

Parameters:

Alpha ($\alpha$): Smoothing factor for the level. 􏰀 

Beta ($\beta $): Smoothing factor for the trend.

Trend Type: Additive or multiplicative.

Dampen Type: Additive or multiplicative. 􏰀 

Phi ($\psi $): Damping coefficient. 

Gamma ($\gamma$ ): Smoothing factor for the seasonality.

Seasonality Type: Additive or multiplicative.

Period: Time steps in seasonal period. 



### 5.3.5 How to Configure Exponential Smoothing 

it is common to use numerical optimization to search for and find the smoothing coefficients (alpha, beta, gamma, and phi) for the model that result in the lowest error.



## 5.6 Summary 

In this tutorial, you discovered naive and classical methods for time series forecasting. Specifically, you learned: 

- 􏰀  How to develop simple forecasts for time series forecasting problems that provide a baseline for estimating model skill. 
- 􏰀  How to develop autoregressive models for time series forecasting. 
- 􏰀  How to develop exponential smoothing methods for time series forecasting. 