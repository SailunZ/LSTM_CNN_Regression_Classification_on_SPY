# LSTM_CNN_Regression_Classification_on_SPY

## Introduction

This project aims to predict the short-term high, low, and exact prices/rate changes/classifications of the SPY ETF using LSTM/CNN/WaveNet neural network models and ensemble learning. 

##  Data

The project utilizes about three months of historical price data and many other features (e.g. technical indicators) as input for the models. The raw data is from Alpha Vantage. More precisely speaking, the inputs are the 2-hour windows of those values. For the CNN model, the inputs are presented as the corresponding graphs. The outputs can be chosen from the high, low, or exact values/percentage changes/classifications in an hour in the future. For example, the high value means the maximum of the SPY prices during the future hour, while the exact value means the exact SPY price one hour later. ![High/Low prices](./data/Screenshots/update1.png "High/Low prices")![Targets](./data/Screenshots/Y.png "Targets")


## Models

Several models were implemented and tested in this project:

- LSTM Regression Model: A deep learning regression model with MAE about $0.4-0.5 for high/low values. ![LSTM](./data/Screenshots/lstm.png "MAE") ![LSTM](./data/Screenshots/lstm_pic.png "Predictions")
- LSTMCNN Regression Model: We combine LSTM and CNN in three different ways with MAE above $0.6. The performances of these regression models may be improved by building a more complex structure and choosing better parameters. ![plot](./data/Screenshots/cnnlstm.png "MAE") ![plot](./data/Screenshots/cnnlstm_pic.png "Predictions")
- WaveNet Regression Model: A deep learning model built from 1d CNN networks with MAE about $0.4-0.5 for high/low values.![plot](./data/Screenshots/wavenet.png "MAE") ![plot](./data/Screenshots/wavenet_pic.png "Predictions")
- Linear Regression Model: A linear regression model with MAE about $0.4-0.5 for high/low values.![plot](./data/Screenshots/linear_pic.png "Predictions")
- Ensemble Model: An ensemble stacking model based on the LSTM/WaveNet/Linear models above via SVR in the end, with MAE around $0.4 for high/low values. ![plot](./data/Screenshots/ensemble_pic.png "Predictions")
- CNN Classification model: The inputs are graphs containing information on prices, MACD, and Signal. ![plot](./data/Screenshots/cnn_batch.png "Batch") A classification model with 5 labels ('hcl' column in Targets) when predicting high values. Accuracy rate: about 25%.![plot](./data/Screenshots/cnn_cls_tr.png "Train") ![plot](./data/Screenshots/cnn_cls_te.png "Test")
- CNNLSTM Classification Model: We put LSTM and CNN in three different ways. Classification models with 5 labels ('hcl' column in Targets) when predicting high values. Accuracy rate: about 30%.![plot](./data/Screenshots/cnnlstm_cls_tr.png "Train") ![plot](./data/Screenshots/cnnlstm_cls_te.png "Test")

## Strategies

One can construct many strategies based on technical indicators and predictive models. We present two of them.

One is based on the features we constructed.![plot](./data/Screenshots/strategy1a.png "Signals")![plot](./data/Screenshots/strategy1b.png "Signals")

The other one utilizes our linear prediction models.![plot](./data/Screenshots/strategy2a.png "Signals")![plot](./data/Screenshots/strategy2b.png "Signals")

## Files

- The names of the notebooks indicate the models being used. "Update.ipynb" updates and preprocesses data on prices and technical indicators from Alpha Vantage. "linear.sav", "lstm.pt", and "wavenet.pt" are saved models/model parameters predicting high values, which are used in "Ensemble Stacking.ipynb". "linear_low.sav" is a saved linear model predicting low values, which is used together with "linear.sav" in "Strategy 2.ipynb". The folder "data" contains CSV files and image files.
