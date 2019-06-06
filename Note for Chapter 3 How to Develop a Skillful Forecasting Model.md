## 3.2 Process overview

1. Define Problem
2. Design Test Harness 
3. Test Models 
4. Finalize Model 

## 3.3 How to Use This Process

- The biggest mistake is skipping steps 
- Having separate code for each experiment that can be re-run at any time 

## 3.4 Step 1 : Define Problem

Define your time series problem. Some topics to consider and motivating questions within each topic (taken from the taxonomy in Chapter 2) are as follows: 

1. Inputs vs. Outputs: What are the inputs and outputs for a forecast? 
2. Endogenous vs. Exogenous: What are the endogenous and exogenous variables? 
3. Unstructured vs. Structured: Are the time series variables unstructured or structured? 
4. Regression vs. Classification: Are you working on a regression or classification predictive modeling problem? What are some alternate ways to frame your time series forecasting problem? 
5. Univariate vs. Multivariate: Are you working on a univariate or multivariate time series problem? 
6. Single-step vs. Multi-step: Do you require a single-step or a multi-step forecast? 
7. Static vs. Dynamic: Do you require a static or a dynamically updated model? 
8. Contiguous vs. Discontiguous: Are your observations contiguous or discontiguous? 

Some useful tools to help get answers include: 

- 􏰀Data visualizations (e.g. line plots, etc.).

- Statistical analysis (e.g. ACF/PACF plots, etc.). 􏰀 

- Domain experts.

- Project stakeholders. 

Update your answers to these questions as you learn more. 



## 3.5 Step 2: Design Test Harness 

Method used to estimate model skill + metric used to evalute predictions 

1. Split the dataset into a train and test set.
2. Fit a candidate approach on the training dataset.

3. Make predictions on the test set directly or using walk-forward validation. 
4. Calculate a metric that compares the predictions to the expected values.  



An important consideration is to ensure that any coefficients used for data preparation are estimated from the training dataset only and then applied on the test set.

## 3.6 Step 3: Test Models 

Some common classes of methods that you can design experiments around include the following: 

1. Baseline: persistence and average 
2. Autoregression: Box-Jenkins, SARIMA
3. Linear regression, LASSO, ridge 
4. Nonlinear Machine Learning: kNN, decision tree, SVM
5. Ensemble machine learning: Random forest, gradient boosting, stacking 
6. Deep learning: MLP, CNN, LSTM, Hybrid models 



Above is univariate. If multivariate, try VAR/VARMA/etc. 

Order here is important and is structured in increasing complexity from classical to modern methods. The
more time and resources that you have, the more configurations that you can evaluate:

- Search model configurations at a finer resolution around a configuration known to already perform well. 
- 􏰀Search more model hyperparameter configurations. 
- 􏰀Use analysis to set better bounds on model hyperparameters to be searched. 
- 􏰀Use domain knowledge to better prepare data or engineer input features. 
- 􏰀Explore different potentially more complex methods. 
- Explore ensembles of well performing base models. 



Include data preparation schemes as parameters for model runs. Some data preparation schems to consider include:

- Differencing to remove a trend.
- Seasonal differencing to remove seasonality. 􏰀
- Standardize to center.
- Normalize to rescale.
- Power Transform to make normal. 

Some ideas to speed up the evaluation of models include: 

- Use multiple machines in parallel via cloud hardware (such as Amazon EC2).

- Reduce the size of the train or test dataset to make the evaluation process faster. 􏰀 

- Use a more coarse grid of hyperparameters and circle back if you have time later. 􏰀 

- Perhaps do not refit a model for each step in walk-forward validation. 

## 3.7  Step 4: Finalize Model 

If the time series is predictable, you will have a list of the top 5 to 10 candidate models that are skillful on the problem. Pick one or multiple models and finalize them.

- Make a prediction for the future.
- Save the model to file for later use in making predictions.
- Incorporate the model into software for making predictions.

Always circle back to the previous step and see if you can further improve upon the final model. This may be required periodically if the data changes significantly
over time.



## 3.9 Further Reading

- Forecasting: principles and practice, 2013. (http://amzn.to/2lln93c)
- Practical Time Series Forecasting with R: A Hands-On Guide, 2016. (http://amzn.to/2k3QpuV)
- Statistical and Machine Learning forecasting methods: Concerns and ways forward, 2018. (http://journals.plos.org/plosone/article?id=10.1371/journal.pone.0194889)



## 3.10 Summary

- 􏰀A systematic four-step process that you can use to work through any time series forecasting problem. 
- 􏰀An list of models to evaluate and the order in which to evaluate them. 
- 􏰀A methodology that allows the choice of a final model to be defensible with empirical evidence, rather than whim or fashion. 