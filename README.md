Real Estate Housing Price Prediction Using Ridge and Lasso Regression

Overview

This project develops and evaluates machine learning models to predict median house values using housing data from California.

The primary objective is to understand how different regression techniques perform on a real-world dataset and investigate how regularization can improve model performance.

Three regression models are implemented and compared:

* Ordinary Least Squares (OLS) Linear Regression
* Ridge Regression (L2 Regularization)
* Lasso Regression (L1 Regularization)

Objectives

* Perform exploratory data analysis (EDA) to understand the dataset.
* Identify missing values and examine relationships between numerical features.
* Apply data preprocessing techniques, including missing-value imputation, feature scaling, and categorical encoding.
* Perform feature engineering to create additional predictive features.
* Train and evaluate OLS, Ridge, and Lasso regression models.
* Use GridSearchCV to tune the regularization parameter for Ridge and Lasso.
* Compare model performance using RMSE, MAE, and R².
* Visualize actual versus predicted values and analyze model residuals.

Dataset

The project uses the California housing dataset available in the Hands-On Machine Learning repository.

The dataset contains housing-related information, including:

* Longitude and latitude
* Median housing age
* Total rooms and bedrooms
* Population
* Number of households
* Median income
* Ocean proximity
* Median house value (target variable)

The target variable is median_house_value, which represents the median house value for a given district.

Note: The dataset contains 20,640 records and includes missing values in the total_bedrooms column. The target values are capped at $500,001 in the original dataset.

Methodology

1. Exploratory Data Analysis

Exploratory data analysis is performed to understand the distribution of housing prices and the relationships between features.

This includes:

* Examining the dataset structure and data types.
* Identifying missing values.
* Visualizing correlations between numerical variables.
* Analyzing the relationship between median income and median house value.
* Examining the distribution of the target variable.

2. Data Preprocessing

A preprocessing pipeline is created using Scikit-learn.

Numerical features:

* Missing values are imputed using the median.
* Features are standardized using StandardScaler.

Categorical features:

* Missing values are imputed using the most frequent value.
* Categorical values are transformed using OneHotEncoder.

The preprocessing steps are incorporated into machine learning pipelines to ensure that transformations are fitted using the training data.

3. Feature Engineering

Two additional features are created to explore potential interactions between housing characteristics:

* income_house_age: Median income multiplied by median housing age.
* income_rooms: Median income multiplied by total rooms.

These features are added to the original predictors to investigate whether interaction effects improve prediction accuracy.

4. Train-Test Split

The dataset is divided into training and testing sets:

* Training set: 80%
* Testing set: 20%

A fixed random state is used to make the split reproducible.

5. Model Training

Ordinary Least Squares Linear Regression

OLS Linear Regression is used as the baseline model. It estimates coefficients by minimizing the sum of squared prediction errors.

Ridge Regression

Ridge Regression applies L2 regularization to penalize large coefficients. GridSearchCV is used to select the regularization parameter (alpha) using five-fold cross-validation.

Lasso Regression

Lasso Regression applies L1 regularization, which can shrink some coefficients to zero. This makes it useful for exploring feature selection.

GridSearchCV is used to tune alpha using five-fold cross-validation.

6. Model Evaluation

The models are evaluated on the held-out test set using three metrics:

* Root Mean Squared Error (RMSE): Measures prediction error while penalizing larger errors more heavily. Lower values are better.
* Mean Absolute Error (MAE): Measures the average absolute difference between actual and predicted house values. Lower values are better.
* R² Score: Measures how much of the variation in the target variable is explained by the model. Higher values are generally better.

7. Visual Analysis

The project includes visualizations to compare model performance and inspect prediction errors:

* Actual versus predicted house values.
* Residual error distributions.
* Residuals versus predicted values.
* Comparison of RMSE, MAE, and R² across the three models.

Lasso coefficients are also examined to investigate which features have the strongest learned effects and how many coefficients have been reduced to zero.

Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook
