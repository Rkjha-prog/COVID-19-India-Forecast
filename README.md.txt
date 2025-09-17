Forecasting COVID-19 Cases in India: A Time Series Analysis
Author: [Radha Krishna Jha]
Date: September 17, 2025
1. Introduction
This notebook presents a time series analysis and forecasting of daily new COVID-19 cases in India. The primary objective is to develop a predictive model that can forecast the trend of new cases for a future period of 30 days based on historical data.

To achieve this, we will employ an ARIMA (AutoRegressive Integrated Moving Average) model, a widely-used statistical method for time series forecasting. The data is sourced from the public repository maintained by the Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE), which provides reliable, daily-updated figures.

The project workflow is structured as follows:

Data Preparation: Loading and transforming the raw data into a usable time series format.
Exploratory Data Analysis (EDA): Visualizing the data to identify underlying trends and patterns.
Modeling: Building and training the ARIMA model.
Forecasting & Conclusion: Generating predictions and summarizing the findings.

2. Data Preparation and Preprocessing
The initial step involves loading the global confirmed cases dataset. The raw data is structured in a wide format, with each column representing a different date.

To prepare the data for time series analysis, we will perform the following key steps:

Filter Data: Isolate the records pertaining to India.
Reshape Data: Convert the wide-format data into a long format, creating a single Date column and a Cumulative_Cases column.
Calculate Daily Cases: Transform the cumulative case counts into daily new case counts by calculating the day-over-day difference. This is the target variable for our model.
Finalize Time Series: Set the Date column as the index to create a clean, univariate time series.

3. Exploratory Data Analysis (EDA)
Before building our model, it's crucial to visualize the time series of daily new cases. This exploratory step allows us to observe the data's primary characteristics, such as:

Trend: The overall long-term direction of the series.
Seasonality: Any recurring cyclical patterns (though less common in this specific context).
Anomalies: Significant spikes or dips, such as infection waves.
By plotting the data, we can gain a better intuition for its behavior, which helps in validating the model's subsequent performance.

4. Modeling with ARIMA
For this forecasting task, we will use the ARIMA model. ARIMA is a powerful class of statistical models that captures temporal structures in time series data. It combines three components:

AutoRegressive (AR - parameter p): A regression model that utilizes the dependent relationship between an observation and some number of lagged observations.
Integrated (I - parameter d): The use of differencing of raw observations to make the time series stationary.
Moving Average (MA - parameter q): A model that uses the dependency between an observation and a residual error from a moving average model applied to lagged observations.
We will train the ARIMA model on the historical daily case data to learn its underlying patterns.

5. Results and Conclusion
After training the model, we use it to forecast the number of daily new cases for the next 30 days. The results are visualized by plotting the forecasted values alongside the historical data to provide a clear comparison and assess the model's predictive trend.

Conclusion: This analysis demonstrates the application of an ARIMA model for forecasting a real-world epidemiological time series. The model provides a baseline prediction that captures the established trend in the data.

It is important to note that this is a univariate model and does not account for external factors like vaccination rates, lockdowns, or new variants, which can cause sudden shifts in trends. For a more robust prediction, future work could involve using a SARIMAX model to include such external variables.