# Air_repository_Beijing



Air Quality Forecasting Using LSTM


**1. Introduction**

Air pollution has severe environmental and health impacts, with PM2.5 being a major contributor to poor air quality. This project aims to predict PM2.5 concentrations in Beijing using historical air quality and weather data. By leveraging recurrent neural networks (RNNs), specifically Long Short-Term Memory (LSTM) networks, we aim to uncover temporal patterns in air pollution levels and enhance predictive accuracy. Our approach involves preprocessing the data, training LSTM models, fine-tuning hyperparameters, and optimizing performance.


**2. Data Exploration & Preprocessing**
Dataset Overview:
The dataset consists of historical air quality measurements, including PM2.5 concentration, temperature, humidity, wind speed, and other meteorological parameters. The data spans multiple years, allowing for the analysis of seasonal trends and temporal dependencies.
Preprocessing Steps:
●	Datetime Conversion: The 'datetime' column was converted to a datetime format and set as the index for time-series analysis.
●	Missing Value Handling: Missing values were filled using mean imputation.
●	Feature Selection: Non-informative columns such as 'No' were dropped.
●	Normalization: The features were scaled using MinMaxScaler to enhance model stability.
●	Data Reshaping: The dataset was reshaped to fit the LSTM model's expected input format (samples, timesteps, features).


**3. Model Design**


The chosen model is a deep LSTM network designed to capture long-term dependencies in time-series data. The best-performing architecture includes:
●	Two LSTM Layers: 128 and 64 units with ReLU activation.
●	Dropout Layers: To prevent overfitting.
●	Dense Output Layer: A single neuron for PM2.5 concentration prediction.
●	Optimizer: Adam, selected for its adaptive learning rate.
●	Loss Function: Mean Squared Error (MSE), optimized for regression tasks.
4. Experiment Table
Experiment #	Parameters	Model Architecture	Output (RMSE)
1	Learning rate = 0.01	Single LSTM layer, 128 units	35.45
2	Learning rate = 0.001, Batch size = 64	Two LSTM layers, 64 units each	29.87
3	Learning rate = 0.001, Dropout = 0.2	Two LSTM layers, 128 & 64 units	27.31
4	Learning rate = 0.0005, Dropout = 0.3	Two LSTM layers, 128 & 64 units	24.85
5	Learning rate = 0.0001, Time steps = 24	Bidirectional LSTM, 128 & 64 units	22.74
5. Results and Discussion
Our experiments show that:
●	Increasing LSTM layers improved feature extraction and reduced RMSE.
●	Lowering the learning rate and adding dropout layers prevented overfitting.
●	A bidirectional LSTM with 24 time steps achieved the best performance, capturing both past and future dependencies.
●	Further hyperparameter tuning, such as batch size adjustments, could yield better results.


**6. Conclusion & Future Work**
This project demonstrated the effectiveness of LSTM models in forecasting PM2.5 concentrations. Our best model achieved an RMSE of 22.74, showing significant improvement over simpler architectures. Future enhancements could include:
●	Implementing attention mechanisms for improved sequence learning.
●	Exploring external factors like traffic and industrial activities.
●	Deploying the model as a real-time forecasting web application.
By refining these approaches, we can enhance air quality prediction accuracy, leading to better public health and environmental outcomes.

