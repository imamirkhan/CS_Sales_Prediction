Link: https://github.com/imamirkhan/CS_Sales_Prediction/blob/main/Price_prediction_models.ipynb

# To forecast monthly product sales for various stores

This project trains and compares various models to forecast the total amount of products sold for every product and store in the next month, given a time-series dataset of daily historical sales. 


## Files

- 'Price_prediction_models.ipynb': Main Jupyter Notebook containing all analysis, visualizations, and modeling.
- 'data folder' : Contains the following files:
	- sales_train.csv: contains the sale count of items, item id and shop id
	- items.csv: contains the item name, id and category
	- item_categories.csv: contains the category name and id
	- shops.csv: contains the shop name and shop id
	- test.csv: data to forecast the final model.
- 'images folder': Contains the graphs 
- 'best_model_xgb': The best model joblib file
- 'README.md': Project overview and summary of findings.

## Key EDA Findings

- Most items were prices below 5k
![sales](https://github.com/imamirkhan/CS_Sales_Prediction/blob/main/images/monthly_sales.png)
- There are seasonal spike around Nov-Dec indicating holiday buying
![monthly sales](https://github.com/imamirkhan/CS_Sales_Prediction/blob/main/images/sales-trend.png)
- There is trend of sales decline over the years and rising average prices over time.
![trend](https://github.com/imamirkhan/CS_Sales_Prediction/blob/main/images/sales-trend.png)

## Modeling Summary

- Dummy Regressor, Linear Regression, Ridge Regression, Decision Tree, Random Forest, XGBoost,LightGBM
- Models were evaluated using RMSE

## Model Performance Comparison

| Model | RMSE | Training Time (s) |
| :--- | :--- | :--- |
| **Random Forest** | **1.26** | 443.58 |
| **XGBoost** | **1.28** | 224.21 |
| **LightGBM** | **1.37** | 51.52 |
| HistGradientBoosting | 1.39 | 744.67 |
| Decision Tree | 1.49 | 48.56 |
| Linear Regression | 1.50 | 4.36 |
| Ridge Regression | 1.50 | 1.89 |
| Dummy Regressor | 2.41 | 0.09 |

## Hypertuning
- Top 3 models were selected for hypertuning. 
- After trying out the models and hyperparameter tuning using optuna, XGBoost model emerged as top performer.
- Regularization and Learning rate tuning in XGBoost helped to achieve balanced bias-varianace trade off.

## SHAP

- item_cnt_month_lag_1 is the most influential feature
- pct_change_lag1 and item_total_popularity also have significant predictive power
- Features like item_cnt_month_lag_2, item_cnt_month_lag_3 and month show smaller but consistent SHAP impacts, indicating mild seasonality and lag persistence.
![trend](https://github.com/imamirkhan/CS_Sales_Prediction/blob/main/images/SHAP.png)

## Conclusion:
The objective of this project was to predict future item sales for various shops. Throuh systematic data cleaning, feature engineering and model optimization, machine learning pipeline is developed to forecast monthly sales.

**Key Takeways and Achievements:**
- Tree-based ensemble models are more robust than linear models because of their ability to handle non-linear and temporal data effectively.
- Temporal and lag based features improved forecasting accuracy.
- Feature engineering and item-shop grid helped to handle seasonal trends, item and store level variations.


## How to Run

1. Clone this repository.
2. Open 'Price_prediction_models.ipynb' in Jupyter Notebook.
3. Run all cells from top to bottom.

## Contact

For questions open an issue or contact via GitHub.

