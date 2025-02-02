# RUL-prediction-of-pronostia-femto-bearing-dataset

Pronostia femto bearing dataset provides run-to-failure (RTF) data for bearings under different operating conditions, allowing researchers to develop models for bearing failure prediction.

## Table of contents

- [Overview of dataset](#overviewofdataset)
- [Objective](#objective) 
- [Exploratory Data Analysis](#exploratorydataanalysis)
- [Training model](#trainingmodel)
- [Evaluating model](#evaluatingmodel)
- [Google collab link](googlecollablink)
  
## Overview of dataset

Dataset 4 consists of a total of 9 distinct bearings, each tested until the end of its
lifespan. These tests were conducted under three different operating conditions.
They are:
First operating condition: 1800 rpm and 4000N (Bearing1_1, Bearing1_2, Bearing1_3)
Second operating condition: 1650 rpm and 4200 N (Bearing2_1, Bearing2_2, Bearing2_3)
Third operating condition: 1500 rpm and 5000 N (Bearing3_1, Bearing3_2, Bearing3_3)
Where Bearingi_j represents bearingj operating under ith operating condition.

## Objective

To predict the Remaining Useful Life (RUL) of bearings at various cycles in the test dataset,
we first need to extract features from the training dataset by analyzing and visualizing the
data. Next, we train a regression model of our choice using these extracted features.
Finally, we apply the same feature extraction process to the test dataset and evaluate it
using the trained regression model.
Finding RMSE between ground truth and predicted values of RUL.
Evaluating the performance of the trained model.

## Exploratory Data Analysis(EDA)

![image alt](https://github.com/user-attachments/assets/326f124e-9955-454d-a16c-a7b1070df8e9)
From the plots, we can clearly observe that torque is not showing any trend due to an outlier. So we can fix a threshold for the torque and we can replace the values outside that threshold with the mean of the data points. We can directly eliminate mean of x and y and standard deviation as rms and standard deviation are same here.

![image alt](https://github.com/user-attachments/assets/bf74ea1d-1397-458b-bba4-814f0b925911)
Even after setting the threshold as µ + 3α and µ - 3α (where µ is mean and α is standard deviation of data points), we were not able to observe any trend. So we removed torque from our features.

![image alt](https://github.com/user-attachments/assets/1d97a0d6-3a4c-4642-ab45-c7388c701c71)
we took magnitude of vibration from x axis and y axis as a single variable and extracted features from it. Here we can take all 4 except standard deviation since it is same as rms. 

## Training model

Now we are ready with our features. We trained linear regression, exponential regression, SVR (support vector regression) and random forest regression models with our features. We have trained 3 different models of each type for each operating condition and tested with their respective test datasets.
After testing, we got our RMSE as 163.47 with random forest model which is comparatively lesser when tested with the other models.

## Evaluating model

![image alt](https://github.com/user-attachments/assets/e1b44139-c30e-46a5-90a3-639e528666b1)
For bearing1_3, every predicted RUL aligns with the actual RUL in the same interval. 
•	A predicted RUL of 1200-1300 matches an actual RUL in the same range.
•	A predicted RUL of 700-800 matches an actual RUL in the same range.
This is a highly accurate result, as there are no off-diagonal entries.

![image alt](https://github.com/user-attachments/assets/28480880-81b2-4b3f-a229-28f018f3db26)

some predictions don’t align perfectly with the actual RUL intervals.
A predicted RUL in the interval 0-100 matches the actual RUL in both 100-200 and 300-400, suggesting underestimation in some cases.

![image alt](https://github.com/user-attachments/assets/536b527a-71de-4ec9-8d7f-06f79bd6b075)

The model overestimates RUL in several instances, as indicated by off-diagonal values.

## code link
[collab](https://colab.research.google.com/drive/121OSoOSrhK0aUwADHSujnK00W2lJ0Jwh?usp=sharing)









