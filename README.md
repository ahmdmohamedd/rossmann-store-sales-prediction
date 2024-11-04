# Rossmann Store Sales Prediction

## Overview

This project aims to predict sales for the Rossmann Store using machine learning techniques, specifically the HistGradientBoostingRegressor model. By analyzing historical sales data, we can generate forecasts that can assist in inventory management and strategic planning. This repository includes the data preprocessing steps, model training, hyperparameter tuning, and evaluation metrics.

## Dataset

The dataset used in this project is the **Rossmann Store Sales** dataset, which contains daily sales data from various Rossmann stores across Germany. The dataset includes various features such as store information, promotion details, and date-related information, making it suitable for time series analysis.

### Dataset Structure

- **Store**: Unique identifier for each store
- **Sales**: Daily sales (target variable)
- **Customers**: Number of customers on that day
- **Open**: Indicator if the store was open (1) or closed (0)
- **Promo**: Indicator if a promotion was running (1) or not (0)
- **StateHoliday**: Indicates if the day is a state holiday
- **SchoolHoliday**: Indicates if the day is a school holiday
- **Date**: Date of the observation
- Other features related to store and promotion

## Installation

To replicate the project on your local machine, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/rossmann-store-sales-prediction.git
   cd rossmann-store-sales-prediction
   ```

2. Install the required packages:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. Open the Jupyter Notebook:
   ```bash
   jupyter notebook rossmann_sales_prediction.ipynb
   ```

2. Run the cells sequentially to load the data, preprocess it, train the model, and evaluate the performance.

## Model Details

The model implemented in this project is the **HistGradientBoostingRegressor** from the `scikit-learn` library. The evaluation metrics used to assess the model performance are:

- **Mean Squared Error (MSE)**: Measures the average squared difference between actual and predicted sales.
- **Mean Absolute Error (MAE)**: Represents the average absolute difference between actual and predicted sales.
- **R-squared (R²)**: Indicates the proportion of variance explained by the model.

### Hyperparameter Tuning

Hyperparameter tuning was performed using `GridSearchCV` to find the optimal combination of parameters for the model. The following parameters were tuned:

- `learning_rate`: Controls the contribution of each tree
- `max_depth`: Maximum depth of the trees
- `max_iter`: Number of boosting iterations
- `min_samples_leaf`: Minimum number of samples required to be at a leaf node

The best parameters found were:
```python
Best Parameters: {'learning_rate': 0.05, 'max_depth': 5, 'max_iter': 100, 'min_samples_leaf': 1}
```

## Results

After training the model, the evaluation metrics obtained were:

- **Best Model MSE**: 946,864.74
- **Best Model MAE**: 723.13
- **Best Model R²**: 0.90

These metrics indicate a good fit of the model to the sales data, with a high R² value suggesting that the model explains a significant portion of the variance in sales.

## Conclusion

This project demonstrates the application of machine learning for sales prediction in a retail context. Future improvements could include exploring additional features, trying different models, or utilizing more advanced techniques like time series forecasting.
