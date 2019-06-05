## 2.1 Framework overview 

Understanding of the structure of your forecast problem, the structure of the model requires, and how to evaluate it. 

1. Inputs vs. outputs
2. Endogenous vs. Exogenous 
3. Unstructured vs. Structured
4. Regression vs. Classification
5. Univariate vs. Multivariate 
6. Single-step vs. Multi-step 
7. Static vs. Dynamic 
8. Contiguous vs. Discontiguous 



## 2.2 Inputs vs. Outputs 

- The goal is to guess about what might happen in the future 
- Input: Historical data, output: Prediction for a future time step beyond the data provided as input 
- Input data is not the data used to train the model
- Think about what exactly is or may be required to make a forecast. For example, identify the variables that could be used to make a forecast 



## 2.3 Endogenous vs. Exogenous 

- __Endogenous__: Input variables that are influenced by other variables in the system and on which the output variable depends. 
- __Exogenous__: Input variables that are not influenced by other variables in the system and on which the output variable depends.
- time series: engogenous variables + may or may not exogenous variables; Strong focus on time seris $\rightarrow$ ignore exogenous
- Some fexibility between these types 



## 2.5 Unstructured vs. Structured. 

- Unstructured: No obvious systematic time-dependent pattern in a time series variable. 
- Structured: Systematic time-dependent patterns in a time series variable (e.g. trend and/or seasonality). 



## 2.6 Univariate vs. Multivariate 

- Univariate: One variable measured over time. 
- Multivariate: Multiple variables measured over time.

## 2.7 Single-step vs. Multi-step 

- One-step: Forecast the next time step.

- Multi-step: Forecast more than one future time steps.



## 2.8 Static vs. Dynamic 

- Static. A forecast model is fit once and used to make predictions.
- Dynamic. A forecast model is fit on newly available data prior to each prediction.



## 2.9 Contiguous vs Discontiguous 

- Contiguous. Observations are made uniform over time.
- Discontiguous. Observations are not uniform over time.



## 2.12 Further readings 

This section provides more resources on the topic if you are looking to go deeper.

- Machine Learning Strategies for Time Series Forecasting, 2013. (http://link.springer.com/chapter/10.1007%2F978-3-642-36318-4_3)
- Recursive and direct multi-step forecasting: the best of both worlds, 2012. (https://econpapers.repec.org/paper/mshebswps/2012-19.htm)



## 2.13 Summary 

In this tutorial, you discovered a framework that you can use to quickly understand and frame your time series forecasting problem. Specifically, you learned: 

- A structured way of thinking about time series forecasting problems. 

- A framework to uncover the characteristics of a given time series forecasting problem. 

- A suite of specific questions, the answers to which will help to define your forecasting problem. 