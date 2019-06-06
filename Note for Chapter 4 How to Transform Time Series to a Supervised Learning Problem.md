## 4.1 Supervised Machine Learning 

Classification, regression



## 4.2 Sliding Window 

Phased as supervised learning problem: using previous time steps as input variables and use the next time step as the output variable:

- The previous time step is the input (X) and the next time step is the output (y) in our supervised learning problem. 

- The order between the observations is preserved, and must continue to be preserved when using this dataset to train a supervised model. 
- 􏰀we have no previous value that we can use to predict the first value in the sequence. We will delete this row as we cannot use it. 
- we do not have a known next value to predict for the last value in the sequence. We may want to delete this value while training our supervised model also. 



This is called sliding window method, or lag method. 

Window width: the number of previous time steps. 

## 4.3 Sliding Window With Multiple Variates 

1. Predict one of multiplevariates $Y_{j}$, using other $X_{i}$ and $Y_{i}$ (i $\neq$ j) as features to predict. 
2. predict all the $Y_{i}$ with the same window width of one. 



## 4.4 Sliding Window With Multiple Steps 

- One-step Forecast: This is where the next time step (t+1) is predicted.

- Multi-step Forecast: This is where two or more future time steps are to be predicted.



## 4.8 Summary 

In this lesson, you discovered how you can re-frame your time series prediction problem as a supervised learning problem for use with machine learning methods. Specifically, you learned: 

- 􏰀Supervised learning is the most popular way of framing problems for machine learning as a collection of observations with inputs and outputs. 
- 􏰀Sliding window is the way to restructure a time series dataset as a supervised learning problem. 
- 􏰀Multivariate and multi-step forecasting time series can also be framed as supervised learning using the sliding window method. 

