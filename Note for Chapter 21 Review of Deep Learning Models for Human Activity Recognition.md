Human activity recognition, or HAR, is a challenging time series classification task. It involves predicting the movement of a person based on sensor data and traditionally involves deep domain expertise and methods from signal processing to correctly engineer features from the raw data in order to fit a machine learning model. Recently, deep learning methods such as convolutional neural networks and recurrent neural networks have shown capable and even achieve state-of-the-art results by automatically learning features from the raw sensor data.



After reading this tutorial, you will know: 

- 􏰀Activity recognition is the problem of predicting the movement of a person, often indoors, based on sensor data, such as an accelerometer in a smartphone. 
- 􏰀Streams of sensor data are often split into subs-sequences called windows, and each window is associated with a broader activity, called a sliding window approach. 
- 􏰀Convolutional neural networks and long short-term memory networks, and perhaps both together, are best suited to learning features from raw sensor data and predicting the associated movement. 



## 21.1 Overview 

This tutorial is divided into five parts; they are:

1. Human Activity Recognition
2. Benefits of Neural Network Modeling
3. Supervised Learning Data Representation
4. Convolutional Neural Network Models
5. Recurrent Neural Network Models 



## 21.2 Human Activity Recognition

Human activity recognition, or HAR for short, is a broad field of study concerned with identifying the specific movement or action of a person based on sensor data. Movements are often typical activities performed indoors, such as walking, talking, standing, and sitting. They may also be more focused activities such as those types of activities performed in a kitchen or on a factory floor. The sensor data may be remotely recorded, such as video, radar, or other wireless methods. Alternately, data may be recorded directly on the subject such as by carrying custom hardware or smartphones that have accelerometers and gyroscopes.

The problem is to predict the activity given a snapshot of sensor data, typically data from one or a small number of sensor types. Generally, this problem
is framed as a univariate or multivariate time series classification task.

It is a challenging problem as there are no obvious or direct ways to relate the recorded sensor data to specific human activities and each subject may perform an activity with significant variation, resulting in variations in the recorded sensor data. __The intent is to record sensor data and corresponding activities for specific subjects, fit a model from this data, and generalize the model to classify the activity of new unseen subjects from their sensor data.__

## 21.3 Benefits of Neural Network Modeling 

Traditionally, methods from the field of signal processing were used to analyze and distill the collected sensor data. Such methods were for __feature engineering, creating domain-specific, sensor-specific, or signal processing-specific features and views of the original data__. Statistical and machine learning models were then trained on the processed version of the data. A limitation of this approach is the signal processing and domain expertise required to __analyze the raw data and engineer the features required to fit a model__. This expertise would be required for each new dataset or sensor modality. In essence, it is expensive and not scalable.

Recently, deep neural network models have started delivering on their promises of feature learning and are achieving stat-of-the-art results for human activity recognition. They are capable of performing automatic feature learning from the raw sensor data and out-perform models fit on hand-crafted domain-specific features.

There are two main approaches to neural networks that are appropriate for time series classification and that have been demonstrated to perform well on activity recognition using sensor data from commodity smartphones and fitness tracking devices. They are Convolutional Neural Network Models and Recurrent Neural Network Models.

1. RNN and LSTM are recommended to recognize __short__ activities that have natural order: RNN could make use of the __time-order relationship__ between sensor readings
2. CNN is better at inferring __long term__ repetitive activities:  CNN is more capable of __learning deep features contained in recursive patterns__.



## 21.4 Supervised Learning Data Representation

Both types of neural networks suitable for time series
classification require that data be prepared in a specific manner in order to fit a model. a 'supervised learning' way that allows the model to associate signal data with an activity class. 

For neural networks involves dividing the
input signal data into windows of signals, where a given window may have one to a few seconds
of observation data. This is often called a __sliding window__.



Each window is also associated with a specific activity. A given window of data may have multiple variables, such as the x, y, and z axes of an accelerometer sensor. Let’s make this concrete with an example. We have sensor data for 10 minutes; that may look like:

x,      y,     z,    activity 

1.1,  2.1, 0.1, 1 

1.2,  2.2, 0.2, 1 

1.3,  2.3, 0.3, 1 

… 



If the data is recorded at 8 Hz, eight rows of data for one second performing an activity. We may choose to have one window of one second of data: eight rows of data for an 8 Hz sensor. If we have x, y, and z data, that means we would have 3 variables. Therefore, a single window of data would be a 2-dimensional array with eight time steps and three features.  

```
[samples, timesteps, features]
```

Larger windows require large models that are slower to train, whereas smaller windows require smaller models that are much easier to fit. __It is common to use one to two seconds of sensor data in order to classify a current fragment of an activity. __

There is some risk that the splitting of the stream of sensor data into windows may result in windows that miss the transition of one activity to another. As such, it was traditionally common to split data into windows with an __overlap__ such that the __first half of the window contained the observations from the last half__ of the previous window, in the case of a 50% overlap.

The use of overlaps, such as a 50% overlap, will double the size of the training data, which may aid in modeling smaller datasets, but may also lead to models that __overfit the training dataset.__



## 21.5 Convolutional Neural Network Models

"When applied to time series classification like HAR, CNN has two advantages over other models: __local dependency and scale invariance__. Local dependency means the nearby signals in HAR are likely to be correlated, while scale invariance refers to the scale-invariant for different paces or frequencies." (**Deep Learning for Sensor-based Activity Recognition: A Survey, 2018.**)

There are many ways to model HAR problems with CNNs. One interesting example was by Heeryon Cho and Sang Min Yoon in their 2018 paper, they divide activities into those that involve movement, called **dynamic**, and those where the subject is stationary, called __static__, then develop a CNN model to __discriminate between these two main classes__. Then, within each class, models are developed to discriminate between activities of that type, such as walking for dynamic and sitting for static. 



Another interesting approach was proposed by Wenchao Jiang and Zhaozheng Yin, they instead combine the signal data together to create images which are then fed to a 2D CNN and processed as image data with convolutions along the time axis of signals and across signal variables, specifically accelerometer and gyroscope data.



## 21.6 Recurrent Neural Network Models

It may be more common to use an __LSTM__ in conjunction with a __CNN__ on HAR problems, in a CNN-LSTM model or ConvLSTM model. This is where a CNN model is used to extract the features from a subsequence of raw sample data, and output features from the CNN for each subsequence are then interpreted by an LSTM in aggregate. 

A deep network architecture is used with four convolutional layers __without any pooling layers__, followed by two LSTM layers to interpret the extracted features over multiple time steps. The authors claim that the removal of the pooling layers is a critical part of their model architecture, where the use of pooling layers after the convolutional layers interferes with the convolutional layers’ ability to learn to downsample the raw sensor data.



## 21.8 Further Reading 

This section provides more resources on the topic if you are looking to go deeper. 

### 21.8.1 General 

- 􏰀Deep Learning for Sensor-based Activity Recognition: A Survey, 2018. https://www.sciencedirect.com/science/article/pii/S016786551830045X 

### 21.8.2 Sliding Windows 

- A Dynamic Sliding Window Approach for Activity Recognition, 2011. https://link.springer.com/chapter/10.1007/978-3-642-22362-4_19 
- 􏰀Window Size Impact in Human Activity Recognition, 2014. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4029702/ 

### 21.8.3 CNNs

- 􏰀Convolutional Neural Networks for Human Activity Recognition using Mobile Sensors, 2014. https://ieeexplore.ieee.org/document/7026300/
- 􏰀Divide and Conquer-Based 1D CNN Human Activity Recognition Using Test Data Sharp- ening, 2018. http://www.mdpi.com/1424-8220/18/4/1055 
- Human Activity Recognition Using Wearable Sensors by Deep Convolutional Neural Networks, 2015.https://dl.acm.org/citation.cfm?id=2806333
- Human activity recognition with smartphone sensors using deep learning neural networks, 2016. https://www.sciencedirect.com/science/article/pii/S0957417416302056

### 21.8.4 RNNs 

- 􏰀Deep Recurrent Neural Networks for Human Activity Recognition, 2017. http://www.mdpi.com/1424-8220/17/11/2556 
- 􏰀Deep Convolutional and LSTM Recurrent Neural Networks for Multimodal Wearable Activity Recognition, 2016. http://www.mdpi.com/1424-8220/16/1/115/html 



## 21.9 Summary 

In this tutorial, you discovered the problem of human activity recognition and the use of deep learning methods that are achieving state-of-the-art performance on this problem. Specifically, you learned: 

- 􏰀Activity recognition is the problem of predicting the movement of a person, often indoors, based on sensor data, such as an accelerometer in a smartphone. 
- 􏰀Streams of sensor data are often split into subs-sequences called windows and each window is associated with a broader activity, called a sliding window approach. 
- 􏰀Convolutional neural networks and long short-term memory networks, and perhaps both together, are best suited to learning features from raw sensor data and predicting the associated movement. 











