# LSTM_CNN_Regression_Classification_on_SPY

## Introduction

This project aims to predict the short-term high, low, and exact prices/classifications of the SPY ETF using LSTM and CNN neural network models. 

##  Data

The project utilizes about three months of historical price data and many other features (e.g. technical indicators) as input for the models. More precisely speaking, the inputs are the 2-hour windows of those values, and the outputs can be the high, low, or exact values/percentages in an hour in the future. For the CNN model, the inputs are presented as the corresponding graphs.


## Models

Several models were implemented and tested in this project:

- LSTM Model: A regression model with RMSE about $0.5 for high/low values. The performance is similar to a linear model.

- CNN Model: The inputs are graphs containing information on prices, MACD, and Signal. A classification model with 5 labels when predicting high values. Accuracy rate: about 25%.

- LSTMCNN Regression: We put LSTM and CNN in three different ways. The performances of these regression models need improvement.

- CNNLSTM classification: We put LSTM and CNN in three different ways. Classification models with 5 labels when predicting high values. Accuracy rate: about 30%.

## Notebooks

- The names of the notebooks indicate the models being used. Update.ipynb updates and preprocesses information on prices and technical indicators from AlphaVantage.
