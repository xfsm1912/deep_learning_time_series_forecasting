## 1.1 Time Series Forecasting

Time series forecasting is difficult: 

1. including order or temporal dependence between observations 
2. temporal structure: trends and seasonality
3. Classical model(ARIMA):    
   - Focus on complete data, missing data unsupported 
   - linear relationship 
   - fixed temporal dependence: relationship between observations at different times must be diagnosed and specified 
   - univariate data
   - one-step forecast



Machine Learning:

1. Effective on: multiple input, complex nonlinear, missing data
2. Disadv: hand-engineered features $\rightarrow$  domain expert or signal processing 



## 1.2 Multiplayer Perceptrons for Time Series 

MLP advantage:

1. Robust to Noise 
2. Nonlinear 
3. Multivariate inputs
4. Multi-step Forecasts



disadvantage:

1. Fixed input 
2. Fixed outputs 
3. have to specify the temporal dependence upfront in the design of the model 



## 1.3 Convolutional Neural Networks for Time Series 

automatically extract the features from the raw data: representation learning 

CNN combine three architectural ideas:

1.  local receptive fields
2. shared weights 
3. spartial or temporal subsampling

CNN yield an effective representation of local salient of the signals 

Key advantage of CNN of feature engineering:

1. task dependent & non hand-crafted manners
2. extracted features have more discriminative power w.r.t the classes of human activities
3. feature extraction and classification are unified in one model so their performances are mutually enhanced 
4. all the advantage of MLP + not require the model to learn directly from lag observations 



## 1.4 Recurrent Neural Network for Time series 

RNN, LSTM

1. __native support for sequence__:  learning a mapping function for the inputs over time to an output.
2. __Learn temporal dependence__: learns what context from the input sequence is useful for the mapping, and can dynamically change this context as needed.



## 1.5 Promise of Deep Learning 

1. Neural networks learn arbitrary mapping functions: Learn the trend and seasonality directly 
2. Not require a scaled ro stationary time series as input 
3. support multivariate inputs
4. support multi-step outputs 
5. Convolutional neural networks support efficient feature learning.
6. LSTM networks support efficient learning of temporal dependencies.
7. Hybrid models efficiently combine the diverse capabilities of different architectures.



## 1.7 Further Reading 

This section provides more resources on the topic if you are looking to go deeper.

- Deep Learning for Time-Series Analysis, 2017. (https://arxiv.org/abs/1701.01887)

- Neural Networks for Time Series Processing, 1996. (http://citeseerx.ist.psu.edu/viewdoc/summary?doi=10.1.1.45.5697)
- Sequence to Sequence Learning with Neural Networks, 2014. (https://arxiv.org/abs/1409.3215)
- Applying LSTM to Time Series Predictable through Time-Window Approaches, 2001. (https://link.springer.com/chapter/10.1007/3-540-44668-0_93)
- Long Short Term Memory Networks for Anomaly Detection in Time Series, 2015. (https://www.elen.ucl.ac.be/Proceedings/esann/esannpdf/es2015-56.pdf)
- Convolutional Networks for Images, Speech, and Time-Series, 1998. (https://dl.acm.org/citation.cfm?id=303704)
- Deep Convolutional Neural Networks On Multichannel Time Series For Human Activity Recognition, 2015. (https://dl.acm.org/citation.cfm?id=2832806)



## 1.8 Summary 

In this tutorial, you discovered the promised capabilities of deep learning neural networks for time series forecasting. Specifically, you learned: 

- The focus and implicit, if not explicit, limitations on classical time series forecasting methods. 
- The general capabilities of Multilayer Perceptrons and how they may be harnessed for time series forecasting. 
- The added capabilities of feature learning and native support for sequences provided by Convolutional Neural Networks and Recurrent Neural Networks. 