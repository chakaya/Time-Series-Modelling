# Time-Series-Modelling

## Objective

The primary objective of this project was to develop a predictive framework for forecasting event registrations for conferences, tailored to distinct audience segments including IT managers, education managers, property managers, and education property managers. The goal was to analyze registration patterns leading up to the start date of each conference and predict the total number of final registrations. This model serves a strategic business function by enabling decision-makers to determine the need for additional advertising. Accurate forecasts are crucial for meeting attendance goals, optimizing marketing budgets, and improving event planning and execution.

## Data Preprocessing

Data preprocessing was crucial in our project, setting the stage for accurate and insightful analysis. We combined datasets for specific target audiences: `D19` and `D21` for IT managers, `NP21` and `GP21` for property managers, and `SRM22` and `SRM23` for education managers. This ensured a comprehensive representation of registration trends across different segments.

A key preprocessing step was calculating daily registrations from the raw data, providing a detailed view of registration patterns over time. Additionally, we calculated Z-scores for daily registrations to identify significant deviations due to external influences, such as advertising campaigns. A Z-score threshold of 2 indicated a probable advertising impact, leading us to create a binary indicator (`0` for no campaign, `1` for campaign presence) for use in our predictive models.

The final dataset included daily registrations, the advertising campaign indicator, and covered the complete date range of the data.

## Modelling Approach

The modeling approach was comprehensive and methodical, employing ARIMA, SARIMAX, and Exponential Smoothing models to forecast event registrations. Each model was selected for its ability to handle time series data, capture trends, seasonal patterns, and external factors' impact.

The ARIMA and SARIMAX models used an automated process, `auto_arima`, for optimal parameter selection, streamlining the model configuration process based on historical data. The SARIMAX model, unlike ARIMA, incorporated advertising campaigns as an exogenous factor, providing insights into marketing strategies' effectiveness on registration numbers.

For training and evaluation, we divided the dataset into an 80/20 split, using 80% of the historical data for training and the remaining 20% for testing. This approach ensured that the models were well-informed by past patterns while being tested against recent data for accuracy.
