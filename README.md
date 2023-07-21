# LSTM-and-GRU-Models
This project aims to implement Long Short Term Memory Model and Gated recurrent unit Model in Python.
The provided code implements LSTM (Long Short-Term Memory) and GRU (Gated Recurrent Unit) models for stock price prediction using the AABA_2006-01-01_to_2018-01-01 dataset. Here's a step-by-step explanation of the code:
1.	Importing Libraries: The necessary libraries are imported, including numpy, pandas, MinMaxScaler, keras, math, and sklearn.metrics.
2.	Accessing Dataset: The dataset is loaded using pandas from the provided CSV file. The dataset contains stock price data for the AABA stock from 2006-01-03 to 2018-01-01, including columns for Date, Open, High, Low, Close, Volume, and Name.
3.	Checking for Missing Values: The 'High' feature (stock price) is chosen for further processing. The training and test sets are created using data up to the year 2016 and data from 2017 onwards, respectively.
4.	Scaling the Training Set: The MinMaxScaler is used to scale the 'High' stock price values to a range of [0, 1].
5.	Preparing Training Sequences for LSTM: The training data is divided into input sequences (X_train) and target values (y_train) for the LSTM model. The LSTM model is designed to predict the current stock price based on the previous 60 stock prices (timesteps).
6.	LSTM Architecture: The LSTM model is constructed using the Keras Sequential API. It consists of four LSTM layers with dropout regularization and a dense output layer.
7.	Compiling and Training the LSTM Model: The LSTM model is compiled with the 'rmsprop' optimizer and the mean squared error loss function. It is then trained on the training data (X_train and y_train) for 25 epochs with a batch size of 32.
8.	Preparing Test Sequences and Predicting with LSTM: The test data is prepared in a similar way as the training data (using 60 previous timesteps). The LSTM model is used to predict the stock prices for the test data, and the predicted values are scaled back to their original range.
9.	Visualizing the Results for LSTM: The predicted stock prices are plotted against the real AABA stock prices for the test set.
10.	Evaluating the LSTM Model: The root mean squared error (RMSE) is calculated to evaluate the performance of the LSTM model on the test set.
11.	GRU Architecture: Similar to the LSTM model, a GRU model is defined using the Keras Sequential API. It also consists of four GRU layers with dropout regularization and a dense output layer.
12.	Compiling and Training the GRU Model: The GRU model is compiled with the 'rmsprop' optimizer and the mean squared error loss function. It is then trained on the training data (X_train and y_train) for 25 epochs with a batch size of 32.
13.	Preparing Test Sequences and Predicting with GRU: The test data is prepared in a similar way as the training data (using 60 previous timesteps). The GRU model is used to predict the stock prices for the test data, and the predicted values are scaled back to their original range.
14.	Visualizing the Results for GRU: The predicted stock prices from the GRU model are plotted against the real AABA stock prices for the test set.
15.	Evaluating the GRU Model: The root mean squared error (RMSE) is calculated to evaluate the performance of the GRU model on the test set.
Both the LSTM and GRU models are used to predict future stock prices based on historical stock price data. The evaluation metrics, RMSE, provide a measure of how well the models perform in predicting the stock prices.
