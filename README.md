# Used Car Price Analysis

This project performs an in-depth analysis of used car prices using a dataset from Kaggle. The objective is to identify key factors that influence the price of a used car and apply different regression models to predict prices accurately. 

## Dataset Description

The dataset includes various features such as year, make, model, trim, body style, engine type, transmission, and location-related data, among others. The target variable is the car's price.


## Link to Noteboook
https://github.com/amystanley25/car-pricing/blob/main/prompt_II.ipynb

## Data Cleaning & Preprocessing

The data was thoroughly cleaned to handle missing values, convert categorical variables, and drop irrelevant or redundant columns. One-hot encoding and polynomial features were used to prepare the dataset for modeling.

## Exploratory Data Analysis (EDA)

Several visualizations and statistical summaries were created to understand data distributions, identify correlations, and gain insights into the factors that impact car prices the most. Outliers and high-cardinality features were also handled appropriately.

## Models Used

Multiple models were employed to predict used car prices. We began with a **Linear Regression** model using **Polynomial Features** to capture non-linear relationships in the data. Next, we applied **Ridge Regression with Polynomial Features**, which incorporates L2 regularization to reduce overfitting while maintaining model complexity. Similarly, **Lasso Regression with Polynomial Features** was used, which applies L1 regularization and can lead to sparse solutions by eliminating less significant features.

In addition, we experimented with **Linear Regression using One-Hot Encoding** on categorical variables, which helped retain more interpretability and avoid introducing unnecessary complexity.

Each model was evaluated using standard metrics like Mean Squared Error (MSE) and R² Score, using cross-validation to ensure robustness and generalization.

## Key Findings

- Linear Regression with Polynomial Features had the best overall performance, achieving an R² score of 0.9326 and a Mean Squared Error (MSE) of 0.0588 on the test set. This suggests that the model effectively captures nonlinear relationships in the data.
 - Ridge Regression with Polynomial Features also performed well, achieving an R² of 0.9085 and MSE of 0.0753. The regularization slightly reduces overfitting, though at a small cost in performance.
- Lasso Regression with Polynomial Features had slightly lower performance with an R² of 0.8856 and MSE of 0.0893. It selected a subset of features, which makes the model more interpretable but less accurate.
- Linear Regression with One-Hot Encoding (without polynomial terms) achieved an R² score of 0.8901 and an MSE of 0.0887. This model performed surprisingly well and offers a more interpretable alternative to polynomial expansion.
- Among categorical features, 'model', 'brand', and 'vehicleType' had the largest impact on price. The one-hot encoded model revealed that certain car models (e.g., 'Golf', 'BMW 3er') and vehicle types (e.g., 'coupe', 'SUV') significantly drive price variation.

## Results & Conclusion

The analysis showed that polynomial features helped capture complex relationships between car attributes and their price. Ridge and Lasso regularization were particularly helpful in reducing overfitting and improving generalization on unseen data. The project illustrates the importance of feature engineering and model selection in a regression pipeline.

## Future Work

- Hyperparameter Tuning:
Perform grid search on Ridge (alpha) and Lasso (alpha) to optimize performance.
Explore different polynomial degrees and interaction-only terms to reduce feature explosion.
- Feature Engineering:
Investigate combining features for better predictors.
Convert registration date and yearOfRegistration into car age for cleaner modeling.
- Model Robustness & Generalization:
Use additional cross-validation strategies to validate stability.
Apply regularization in linear models with one-hot encoding to prevent multicollinearity.
- Explore Other Models:
Try Random Forest Regressor, Gradient Boosting, or XGBoost to see if tree-based models outperform linear ones on this dataset.
