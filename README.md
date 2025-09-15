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
	- 
- 'README.md': Project overview and summary of findings.

## Modeling Summary

- Linear Regression, Ridge Regression, ARIMA, Decision Tree, Random Forest, KNN, XGBoost
- Models are evaluated using RMSE


## Key Findings

- There are seasonal spike around months 11 & 23 indicating holiday buying
- There is trend of sales decline over the years and rising average prices over time.
- KNN and RandomForest are the top performing models so far

## How to Run

1. Clone this repository.
2. Open 'Price_prediction_models.ipynb' in Jupyter Notebook.
3. Run all cells from top to bottom.

## Contact

For questions open an issue or contact via GitHub.

