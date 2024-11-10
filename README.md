# Sales Forecasting Dashboard

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Requirements](#requirements)
- [Project Explanation](#project-explanation)
  - [Data Collection](#data-collection)
  - [Data Preprocessing](#data-preprocessing)
  - [Time Series Forecasting](#time-series-forecasting)
  - [Interactive Dashboard](#interactive-dashboard)
- [Acknowledgements](#acknowledgements)

## Overview
This project is a Sales Forecasting Dashboard that predicts future sales based on historical sales data. It uses time series forecasting methods (such as ARIMA) to generate a 30-day sales forecast. The dashboard is built using Dash and Plotly for interactive data visualization, making it easy for users to explore and visualize sales trends and forecasts.

## Features
- **Time Series Forecasting:** The model uses the ARIMA method to predict sales for the next 30 days based on historical data.
- **Interactive Visualization:** The dashboard allows users to interactively view historical sales data and forecasted values using Plotly graphs.
- **Data Exploration:** Users can visually analyze sales trends, inventory levels, and price changes over time.
- **Forecasting Insights:** The dashboard offers insights into potential future sales trends to support decision-making.

## Requirements
To run the project locally, you need to have the following Python packages installed:
- **Dash**: For creating the interactive web application.
- **Plotly**: For generating the interactive graphs.
- **Pandas**: For data manipulation and analysis.
- **Matplotlib**: For plotting static graphs.
- **Seaborn**: For creating attractive statistical visualizations.
- **Statsmodels**: For time series modeling (ARIMA).
- **Kaggle**: For downloading the dataset from Kaggle.

Additionally, you may want to use:
- Python 3.7+
- Virtual environment setup (`virtualenv` or `conda`)
- `requirements.txt` (optional) for easier package installation

## Project Explanation
### Data Collection
The dataset used for this project contains historical sales data, inventory, and pricing details. It was downloaded from Kaggle and includes daily sales, inventory, and price records. The raw data was cleaned and preprocessed to handle missing values and ensure the correct data types were assigned for each column.

### Data Preprocessing
- **Datetime Conversion:** The 'data' column was converted to datetime format to allow for time-based analysis.
- **Handling Missing Values:** Missing values were filled using forward filling (ffill), ensuring no gaps in the time series data.
- **Correlation Analysis:** A correlation matrix was generated to explore relationships between sales, inventory, and price, which helped in understanding their mutual dependencies.

### Time Series Forecasting
I applied ARIMA (AutoRegressive Integrated Moving Average) for time series forecasting, which is a widely used method for predicting future values based on past observations. The ARIMA model was chosen due to its effectiveness in handling univariate time series data.
- **ADF Test for Stationarity:** Before applying ARIMA, I performed the Augmented Dickey-Fuller (ADF) test to check whether the data was stationary. Since non-stationary data can lead to inaccurate forecasts, differencing was applied to make the data stationary.
- **Model Fitting:** The ARIMA model was fit on the historical sales data with parameters (5,1,0) representing the AR, I (Integrated), and MA (Moving Average) components.
- **Forecasting:** Using the fitted ARIMA model, I forecasted the sales for the next 30 days. The forecast was then visualized on the dashboard, along with historical sales data.

### Interactive Dashboard
The dashboard was built using Dash and Plotly to provide interactive data visualization. Users can view historical sales trends, forecasts, and explore the relationship between sales, inventory, and price through various visualizations.
- **Line Graphs:** Sales, inventory, and price trends were plotted over time using line graphs.
- **Forecasting Visualization:** The forecasted sales for the next 30 days were shown alongside the historical sales data, making it easy to visualize future trends.

## Acknowledgements
- The sales data used in this project was sourced from Kaggle.
- The ARIMA time series forecasting model is implemented using the Statsmodels library.
- Thanks to the Dash and Plotly teams for providing the interactive framework and visualization tools.
