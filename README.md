# House Price Prediction

## Project Overview

This project predicts residential house prices using machine learning. It uses property characteristics and location information from a Washington State, USA housing dataset.

## Dataset

- Original records: 4,600
- Records used for modeling: 4,551
- Zero-priced records excluded: 49
- Target variable: `price`
- Training records: 3,640
- Testing records: 911

Zero-priced records were excluded because they cannot provide meaningful sale-price targets for this prediction task.

## Features Used

The model uses 14 features:

- Bedrooms and bathrooms
- Living area and lot area
- Floors, waterfront, view, and condition
- Above-ground and basement area
- Year built and year renovated
- City and ZIP code

## Data Preprocessing

- Numerical features were standardized using `StandardScaler`.
- Categorical features were encoded using `OneHotEncoder`.
- Unknown categorical values are handled with `handle_unknown="ignore"`.
- The data was split into training and testing sets using an 80:20 ratio and `random_state=42`.

## Models Evaluated

Three regression algorithms were compared:

1. Linear Regression
2. Random Forest Regressor
3. Gradient Boosting Regressor

## Model Performance

| Model | MAE | RMSE | R² |
|---|---:|---:|---:|
| Linear Regression | $119,155.91 | $213,151.50 | 0.6946 |
| Random Forest | $128,081.23 | $501,027.56 | -0.6874 |
| Gradient Boosting | $126,832.79 | $280,893.55 | 0.4696 |

Linear Regression performed best among the three evaluated models on the current test set.

## Evaluation Metrics

- **MAE:** Mean Absolute Error
- **RMSE:** Root Mean Squared Error
- **R²:** Coefficient of determination

## Saved Artifacts

- `models/house_price_model.pkl` — trained Linear Regression pipeline
- `outputs/model_comparison.csv` — comparison of model evaluation metrics
- `outputs/graphs/` — project visualizations

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Joblib
- Jupyter Notebook

## Limitations and Future Improvements

- Investigate unusually high-priced properties for potential data-quality issues.
- Examine the large prediction errors produced by Random Forest.
- Evaluate performance across different price ranges and locations.
- Explore feature engineering and model tuning.
- Validate the model on additional unseen data before considering production use.

## Conclusion

The project demonstrates a complete regression workflow, including data exploration, preprocessing, model training, evaluation, comparison, and model serialization. Linear Regression was the strongest model among the three tested on the current holdout set.
