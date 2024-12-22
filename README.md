# Walmart Sales Prediction

## Overview
This project involves predicting weekly sales for Walmart stores using various regression techniques. The dataset contains store-specific features and economic indicators to explore linear and non-linear relationships with the target variable (`Weekly_Sales`).

## Dataset Details
- **Number of Samples**: 6435 rows
- **Number of Features**: 8 columns
- **Features**:
  - `Store`: Store identifier
  - `Date`: Week date
  - `Weekly_Sales`: Weekly revenue
  - `Holiday_Flag`: Indicates whether the week is a holiday week
  - `Temperature`: Average temperature
  - `Fuel_Price`: Cost of fuel
  - `CPI`: Consumer Price Index
  - `Unemployment`: Unemployment rate
- **Target Variable**: `Weekly_Sales`

## Key Steps and Methodology

### 1. **Data Preprocessing**
- **Null Values**: No nulls in the dataset; imputation was unnecessary.
- **Feature Engineering**: 
  - Extracted `month` and `year` from `Date`.
  - Encoded the `Store` feature using binary encoding.
- **Outlier Handling**: Applied IQR-based outlier removal for continuous features.
- **Scaling**: Used MinMaxScaler and StandardScaler for feature normalization.

### 2. **Exploratory Data Analysis**
- **Correlation Analysis**: Generated Pearson Correlation Coefficients to assess feature relationships.
- **Visualization**: Histograms, density plots, and scatter plots were created to explore data distributions and relationships.

### 3. **Model Implementation**
#### **Linear Models**
1. **Linear Regression**:
   - Implemented using the Normal Equation and Stochastic Gradient Descent (SGD).
   - Conducted 3-fold cross-validation.
   - Performance Metrics:
     - Mean Squared Error (MSE)
     - R² Score
2. **Regularized Linear Models**:
   - **Ridge Regression** (L2 Regularization)
   - **Lasso Regression** (L1 Regularization)
   - **Elastic Net** (Combination of L1 and L2)
   - Hyperparameter tuning was performed for `alpha`.

#### **Polynomial Regression**
- Extended the linear regression model to include polynomial features for non-linear relationships.
- Implemented Ridge, Lasso, and Elastic Net regularization for polynomial regression.

### 4. **Hyperparameter Tuning**
- Conducted experiments with varying `alpha` values, learning rates, and batch sizes for SGD models.
- Utilized K-fold cross-validation to identify optimal model configurations.

### 5. **Evaluation Metrics**
- MSE: Measures average squared error between actual and predicted values.
- R² Score: Indicates the proportion of variance explained by the model.

### 6. **Learning Curves**
- Generated learning curves to evaluate the model's generalization and identify potential underfitting or overfitting.

## Key Results
- **Linear Models**:
  - **Ridge Regression** with alpha=0.01 performed best among linear models with an MSE of ~234.9 billion.
- **Polynomial Models**:
  - Polynomial Ridge Regression achieved an MSE of ~73.2 billion at degree=2 with alpha=0.01.
- **Regularization Observations**:
  - Ridge and Lasso were effective for reducing overfitting.
  - Elastic Net was less effective with higher alpha values.

## Future Work
1. **Explore Advanced Models**: Test tree-based models (e.g., Random Forest, Gradient Boosting) or neural networks.
2. **Feature Engineering**: Investigate interaction terms and higher-order features beyond polynomial transformations.
3. **Hyperparameter Optimization**: Apply Bayesian optimization or grid search for tuning.
4. **Data Balancing**: Consider synthetic methods like SMOTE to address imbalanced data distributions.

## Dependencies
- Python 3.11.4
- Libraries:
  - pandas
  - numpy
  - scikit-learn
  - seaborn
  - matplotlib
  - category_encoders
  - scipy

## Conclusion
This project provides insights into leveraging linear and polynomial regression techniques to predict Walmart's weekly sales while emphasizing feature engineering, regularization, and hyperparameter tuning.

--- 

You can modify this content as needed! Let me know if you'd like further adjustments.
