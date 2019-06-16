An important recent study evaluated and compared the performance of many classical and modern machine learning and deep learning methods on a
large and diverse set of more than 1,000 univariate time series forecasting problems. This study suggest that simple classical methods, such as linear methods and exponential smoothing, outperform complex and sophisticated methods, such as decision trees, Multilayer Perceptrons (MLP), and Long Short-Term Memory (LSTM) network models.



- Classical methods like ETS and ARIMA out-perform machine learning and deep learning methods for one-step forecasting on univariate datasets. 

- Classical methods like Theta and ARIMA out-perform machine learning and deep learning methods for multi-step forecasting on univariate datasets. 

- Machine learning and deep learning methods do not yet deliver on their promise for univariate time series forecasting, and there is much work to do. 



## 10.1 Overview 

Spyros Makridakis, et al. published a study in 2018 titled *Statistical and Machine Learning forecasting methods: Concerns and ways forward*. This tutorial is
divided into seven sections; they are:

1. Study Motivation
2. Time Series Datasets
3. Time Series Forecasting Methods
4. Data Preparation
5. One-step Forecasting Results
6. Multi-step Forecasting Results
7. Outcomes



## 10.2 Stuty Motivation

The goal of the study was to clearly demonstrate the capability of a suite of different machine learning methods as compared to classical time series forecasting methods on a very large and diverse collection of univariate time series forecasting problems. 

The authors clearly lay out three issues with the flood of claims; they are:

- 􏰀Their conclusions are based on a few, or even a single time series, raising questions about the statistical significance of the results and their generalization. 
- 􏰀The methods are evaluated for short-term forecasting horizons, often one-step-ahead, not considering medium and long-term ones. 
- 􏰀No benchmarks are used to compare the accuracy of ML methods versus alternative ones. 



## 10.3 Time series Datasets

The time series datasets used in the study were drawn from the time series datasets used in the
M3-Competition. 



## 10.4 Time Series Forecasting Methods

The study evaluates the performance of eight classical (or simpler) methods and 10 machine learning methods.

The eight classical methods evaluated were as follows: 

- Naive 2, which is actually a random walk model adjusted for season. 􏰀 
- Simple Exponential Smoothing.
- Holt.
- Damped exponential smoothing. 
- Average of SES, Holt, and Damped. 􏰀 
- Theta method.
- ARIMA, automatic.
- ETS, automatic. 

A total of eight machine learning methods were used in an effort to reproduce and compare to results presented in the 2010 paper *An Empirical Comparison of Machine Learning Models for Time Series Forecasting*. 

- Multilayer Perceptron (MLP).
- Bayesian Neural Network (BNN).
- Radial Basis Functions (RBF).
- Generalized Regression Neural Networks (GRNN), also called kernel regression.
- k-Nearest Neighbor regression (KNN).
- CART regression trees (CART).
- Support Vector Regression (SVR).
- Gaussian Processes (GP).



An additional two modern neural network algorithms were also added to the list given the recent rise in their adoption; they were:

- Recurrent Neural Network (RNN).
- Long Short-Term Memory (LSTM).



## 10.5 Data Preparation

Variations of five different data transforms were applied for an MLP for one-step forecasting and their results were compared. The five transforms were: 

- Original data.
- Box-Cox Power Transform.
- Deseasonalizing the data.
- Detrending the data
- All three transforms (power, deseasonalize, detrend).

## 10.6 One-step Forecasting Results

All models were evaluated using one-step time series forecasting. Specifically, the last 18 time steps were used as a __test set__, and models were fit on all remaining observations. A separate one-step forecast was made for each of the 18 observations in the test set, presumably using a walk-forward validation method where true observations were used as input in order to make each forecast.

1. Reviewing the results, the MLP and BNN were found to achieve the best performance from
   all of the machine learning methods.
2. An interesting result was that RNNs and LSTMs were found to perform poorly. LSTMs are easily outperformed by simpler methods and may not be suited to simple autoregressive-type univariate time series forecasting problems.
3. machine learning methods were all out-performed by simple classical methods, where ETS and ARIMA models performed the best overall. 



## 10.7 Multi-step Forecasting Results

Multi-step forecasting involves predicting multiple steps ahead of the last known observation. Three approaches to multi-step forecasting were evaluated for the machine learning methods; they were:

- Iterative forecasting
- Direct forecasting
- Multi-neural network forecasting

The classical methods were found to outperform the machine learning methods again.



## 10.8 Outcomes

The study provides important supporting evidence that classical methods may dominate univariate time series forecasting, at least on the types of forecast in problems evaluated. 

These findings strongly encourage the use of __classical methods__, such as ETS, ARIMA, and others as a first step before more elaborate methods are explored, and requires that the results from these simpler methods be used as a __baseline in performance__ that more elaborate methods must clear in order to justify their usage. It also highlights the need to not just consider the careful use of __data preparation methods__, but to actively test multiple __different combinations of data preparation__ schemes for a given problem in order to discover what works best, even in the case of classical methods.

They comment that LSTMs appear to be more suited at fitting or __overfitting__ the training dataset rather than forecasting it. 



## 10.10 Further Reading 

This section provides more resources on the topic if you are looking to go deeper. 

- 􏰀  Makridakis Competitions, Wikipedia. 

  https://en.wikipedia.org/wiki/Makridakis_Competitions

- 􏰀  The M3-Competition: Results, Conclusions and Implications, 2000. https://www.sciencedirect.com/science/article/pii/S0169207000000571 

- 􏰀  The M4 Competition: Results, findings, conclusion and way forward, 2018. https://www.sciencedirect.com/science/article/pii/S0169207018300785 

- 􏰀  Statistical and Machine Learning forecasting methods: Concerns and ways forward, 2018. http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0194889 

- 􏰀  An Empirical Comparison of Machine Learning Models for Time Series Forecasting, 2010. https://www.tandfonline.com/doi/abs/10.1080/07474938.2010.481556 

- 􏰀  Applying LSTM to Time Series Predictable through Time-Window Approaches, 2001. https://link.springer.com/chapter/10.1007/3-540-44668-0_93 



## 10.11 Summary 

In this tutorial, you discovered the important findings of a recent study evaluating and comparing the performance of classical and modern machine learning methods on a large and diverse set of time series forecasting datasets. Specifically, you learned: 

- 􏰀  Classical methods like ETS and ARIMA out-perform machine learning and deep learning methods for one-step forecasting on univariate datasets. 
- 􏰀  Classical methods like Theta and ARIMA out-perform machine learning and deep learning methods for multi-step forecasting on univariate datasets. 
- 􏰀  Machine learning and deep learning methods do not yet deliver on their promise for univariate time series forecasting and there is much work to do. 