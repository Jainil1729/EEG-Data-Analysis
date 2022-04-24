# EEG-Data-Analysis
The original dataset from the reference consists of 5 different folders, each with 100 files, with each file representing a single subject/person. Each file is a recording of brain activity for 23.6 seconds. The corresponding time-series is sampled into 4097 data points. Each data point is the value of the EEG recording at a different point in time. So we have total 500 individuals with each has 4097 data points for 23.5 seconds.

Every 4097 data points were shuffled into 23 chunks, each chunk contains 178 data points for 1 second, and each data point is the value of the EEG recording at a different point in time. So now we have 23 x 500 = 11500 pieces of information(row), each information contains 178 data points for 1 second(column), the last column represents the label y {1,2,3,4,5}.

The response variable is y in column 179, the Explanatory variables X1, X2, ..., X178

y contains the category of the 178-dimensional input vector. Specifically y in {1, 2, 3, 4, 5}:

5 - eyes open, means when they were recording the EEG signal of the brain the patient had their eyes open

4 - eyes closed, means when they were recording the EEG signal the patient had their eyes closed

3 - Yes they identify where the region of the tumor was in the brain and recording the EEG activity from the healthy brain area

2 - They recorder the EEG from the area where the tumor was located

1 - Recording of seizure activity

NOTE: The extracted features dataset used is a big file (143 MB) and hence, can't be uploaded directly on Github. Please access the file via this link: https://drive.google.com/file/d/1nCQQKEFVWBaAAXCoUDMqKj84cC7IRcJw/view?usp=sharing

All subjects falling in classes 2, 3, 4, and 5 are subjects who did not have epileptic seizure. Only subjects in class 1 have epileptic seizure. Our motivation for creating this version of the data was to simplify access to the data via the creation of a .csv version of it. Although there are 5 classes most authors have done binary classification, namely class 1 (Epileptic seizure) against the rest.

End Goal: 1) Detecting Seizure 2) Multiclass classification
Approach
1) Detecting Seizure: Multiple classification models were tested using time domain data for detecting epilepsy using binary classification
2) Multiple class classification using Time Domain Data
3) Multiple class classification using Frequency Domain Data ( decomposed signal )
4) Multiple class classification using Frequency Domain Data ( combined signals )
4) Multiple class classification using features extracted from the EEG signals using tsfresh library (decomposed signals )
5) Implementation of a Neural Network for multiple class classification

Conclusion: 
1. Binary Classification: The Extreme Random Forest model resulted in a 96% accuracy.
2. Multi Class Classification: After Optimising the hyperparametes and selecting best features, the model gave highest accuracy of 82%. 
3. Implementing Neural Networks model (LSTM) didn't improve the multi class classification and gave measly results.
