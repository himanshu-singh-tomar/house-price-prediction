# Executive Summary — House Price Prediction

## Project Overview

The House Price Prediction project aims to estimate residential property prices using machine learning techniques. The project uses a housing dataset containing 4,600 records from Washington State, USA, with property characteristics such as bedrooms, bathrooms, living area, lot size, construction year, condition, and location.

## Data Preparation

The dataset was inspected and prepared for modeling. A total of 49 properties with zero recorded prices were excluded because they did not provide meaningful target values for price prediction. The resulting modeling dataset contained 4,551 records.

Numerical features were standardized using `StandardScaler`, while categorical features, including city and ZIP code, were encoded using `OneHotEncoder`. The cleaned dataset was divided into training and testing sets using an 80:20 split, resulting in 3,640 training records and 911 testing records.

## Machine Learning Models

Three regression algorithms were trained and evaluated:

1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor

The models were compared using Mean Absolute Error (MAE), Root Mean Squared Error (RMSE), and the coefficient of determination (R²).

## Results

Linear Regression achieved the best performance among the three evaluated models on the current test set.

- **MAE:** $119,155.91
- **RMSE:** $213,151.50
- **R² score:** 0.6946

These results indicate that the model explains approximately 69.46% of the variation in house prices in the test set. The average absolute prediction error is approximately $119,156, which is substantial and should be considered when interpreting individual estimates.

Random Forest and Gradient Boosting performed worse on this test set. Random Forest produced a negative R² score, indicating poor predictive performance relative to a simple mean-price baseline.

## Model Deployment Readiness

The selected Linear Regression pipeline, including its preprocessing steps, was saved using Joblib. The saved pipeline was successfully reloaded and tested on example property inputs, demonstrating that it can generate predictions for new records with the required features.

These example predictions validate the prediction workflow, but they do not independently establish real-world accuracy because verified sale prices were not available for the example properties.

## Conclusion and Future Improvements

The project demonstrates a complete machine learning workflow, including exploratory data analysis, data preparation, model training, evaluation, comparison, model serialization, and prediction on new inputs.

Future improvements should include investigating extreme-price records, analyzing errors across different price ranges and locations, performing more extensive model validation, and evaluating the model on a separate dataset containing verified sale prices.

Overall, Linear Regression is the strongest of the three models evaluated in this experiment, while additional validation and data-quality investigation are recommended before real-world use.