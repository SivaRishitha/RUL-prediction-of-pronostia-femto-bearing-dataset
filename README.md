# RUL-prediction-of-pronostia-femto-bearing-dataset

Pronostia femto bearing dataset provides run-to-failure (RTF) data for bearings under different operating conditions, allowing researchers to develop models for bearing failure prediction.

## table of contents

- [Overview of dataset](https://github.com/SivaRishitha/RUL-prediction-of-pronostia-femto-bearing-dataset/edit/main/README.md#overview-of-dataset)

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



