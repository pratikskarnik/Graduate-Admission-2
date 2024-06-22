# Graduate Admission Prediction

This repository contains the code and datasets for my master thesis project at LJMU, which aims to predict the admission probabilities of international students applying for graduate programs.

## Objective

The primary goal of this project is to develop a predictive model that estimates the probability of international students being admitted to graduate programs based on various features of their application profiles.

## Datasets

The project utilizes two datasets:
1. `Admission_Predict.csv`
2. `Admission_Predict_Ver1.1.csv`

These datasets include the following features:
- GRE Score
- TOEFL Score
- University Rating
- Statement of Purpose (SOP)
- Letter of Recommendation (LOR)
- CGPA (Cumulative Grade Point Average)
- Research (whether the student has research experience)
- Chance of Admit (target variable)

## Approach

The project explores two main approaches:
1. **With Target Transformation**
2. **Without Target Transformation**

### 1. With Target Transformation

#### Data Preprocessing
- **Standardization**: Features are standardized using `StandardScaler` to normalize the data.
- **Transformation**: The target variable, `Chance of Admit`, is transformed using a sigmoid function to handle non-linearity and improve model performance.

#### Exploratory Data Analysis (EDA)
- **Pair Plots**: Visual analysis to observe relationships between features.
- **Correlation Matrix**: Heatmap to identify the correlation between different features and the target variable.

#### Feature Engineering
- The `Chance of Admit` is transformed using a custom function (`rev_sigmoid`) for better linearity in modeling.

#### Modeling
- **Linear Regression**: Built an initial linear regression model to establish a baseline.
- **OLS Regression**: Used Ordinary Least Squares (OLS) for regression analysis, evaluating the model with significant features.
- **Feature Selection**: Dropped less significant features based on p-values and multicollinearity using Variance Inflation Factor (VIF).

#### Advanced Models
- **Random Forest Regressor**: Employed ensemble learning methods to capture complex patterns in the data.
- **XGBoost Regressor**: Used gradient boosting for improved prediction accuracy.
- **CatBoost**: Implemented CatBoost regressor optimized through hyperparameter tuning using Optuna.

#### Evaluation
- Models are evaluated based on metrics such as Mean Squared Error (MSE), R-squared (R²), and Mean Absolute Error (MAE).
- The final model’s predictions are transformed back using the sigmoid function for interpretation.

### 2. Without Target Transformation

#### Data Preprocessing
- Similar standardization techniques are applied without transforming the target variable.

#### Modeling
- Followed the same modeling pipeline with linear regression, OLS, Random Forest, XGBoost, and CatBoost.
- Hyperparameter tuning and feature selection processes are conducted similarly.

#### Evaluation
- Compared the performance of models with and without target transformation to determine the impact of the transformation on prediction accuracy.

## Results

The project demonstrates how different machine learning models can be utilized to predict the admission probabilities of students. It also highlights the importance of data transformation and feature selection in improving model performance.

## Conclusion

Through rigorous data preprocessing, feature engineering, and model evaluation, the project provides a comprehensive analysis and solution for predicting graduate admission probabilities. The results can assist universities in making informed decisions based on applicant profiles.

## Repository Contents

- `Admission_Predict.csv`: Original dataset.
- `Admission_Predict_Ver1.1.csv`: Updated dataset with additional features.
- `With target transformation.ipynb`: Jupyter notebook for the approach with target transformation.
- `Without target transformation.ipynb`: Jupyter notebook for the approach without target transformation.
- `README.md`: Project documentation.
- `LICENSE`: License information.

## License

This repository is licensed under the MIT License. See LICENSE for details.

## Acknowledgments

This research was conducted as part of Pratik Smitin Karnik's MS in Data Science studies at Liverpool John Moores University.
