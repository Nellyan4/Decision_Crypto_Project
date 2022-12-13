# Decision_Crypto_Project

### Topic: Cryptocurrency Price Prediction and Investment Portfolio Optimization
### Group 12: Elaine Zhang, Xi Yan, Xintong Zheng, Wei Xiao, Jingbo Zhang

# Preprocessing:
**Code file**: ***Preprocessing.ipynb***

**Input**: Raw data for the whole project: 93 csv files in the folder called “data”, with the name of each cryptocurrency as the name of the file
Output for Prediction: Since we need to run models for all cryptocurrencies, we build the demo pipelines in this file but actually attach the pipeline with models in the Prediction part.

**Output for Optimization**: 
1. ***op_data_1.csv***: processed data for short-term optimization, features for each cryptocurrency include “Name”, “Open” and “Close”
2. ***op_data_3.csv***: processed data for long-term optimization, rows are dates from 2021-07-28 to 2021-08-28, columns are 93 cryptocurrencies, values are close price

# Machine Learning:
**Code file**: ***ML_prediction.ipynb***

**Input**: Raw data for the whole project: 93 csv files in the folder called “data”

**Description**: 
It consists of two sections. The first section is what we tested in our Machine Learning model for one random cryptocurrency bitcoin dataset. This section includes detailed implementations of the ML model on the bitcoin dataset and prints out every implementation step with graphs, i.e., model evaluation, graph of predicted data compared to actual dataset.
Moving on, in the second section, we auto-applied the modeling process to all the 93 csv files called “data”, which are the input of the ML model. The process is almost identical to the previous section. The only difference is that we did not plot the result of every step. The output is selected by which model generate the minimal sum of residual.

**Notice**: There will be two temporary file generated in the jupyter notebook: ***tmp_ML_27.csv*** and ***tmp_ML_28.csv***, if there are already in the folder, you need to delete them first.

**Output**: ***output_ML.csv***, which includes the crypto name, actual close price on Aug 27th, % change, actual open price on Aug 28th, and predicted close price on Aug 28th. And it becomes the input for the optimization model.

# ARIMA:
**Code file**: *ARIMA_prediction.ipynb*

**Description**: 
It consists of two sections. The first section is what we tested in our ARIMA model for one random cryptocurrency bitcoin dataset. This section includes detailed implementations of the ARIMA model on the bitcoin dataset and prints out every implementation step with graphs, i.e., how we processed the dataset, how we dealt with stationarity and eliminated the trend, and how we found the optimal parameters.
Moving on, in the second section, we auto-applied the modeling process to all the 93 csv files called “data”, which are the input of the ARIMA model. The process is almost identical to the previous section. The only difference is that we did not plot the result of every step. 

**Input**: Raw data for the whole project: 93 csv files in the folder called “data”.

**Output**: ***output_ARIMA.csv***, which includes the crypto name, actual open price on Aug 28th, and predicted close price on Aug 28th. And it becomes the input for the optimization model.

# Optimization:
Optimization only has one code file: ***Optimization.ipynb***, you could run all cells at once. It has multiple sections in the code file:
1. Short-term optimization - Maximize Expected Profits on One Specific Day, imported data from ***op_data_1.csv***
2. Short-Term Optimization - Maximize Expected Profits on One Specific Day Using Machine Learning Prediction Results, using data from ***output_ML.csv***
3. Short-Term Optimization - Maximize Expected Profits on One Specific Day Using ARIMA Prediction Results, using data from ***output_ARIMA.csv***
4. Long-Term Optimization - Optimize Expected Profits while Minimizing Portfolio Risk, read data from ***op_data_3.csv***
