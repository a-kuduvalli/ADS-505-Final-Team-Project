# ADS-505-Final-Team-Project

This project is a part of the ADS-505 course in the Applied Data Science Program at the University of San Diego.

**Project Status: [Active]**

# Installation

To use this project, first clone the repository on your device using the command below:

  ```bash
git clone https://github.com/a-kuduvalli/ADS-505-Final-Team-Project.git
cd ADS-505-Final-Team-Project
   ```
Then:
1. Install the libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost
```

2. Download the Doordash ETA Prediction dataset `historical_data.csv` from [Kaggle](https://www.kaggle.com/datasets/dharun4772/doordash-eta-prediction/data).
3. Save `historical_data.csv` in the same folder as `___`
4. Run all cells in `____`.

# Project Introduction / Objective

Delivery time is a critical part of the customer experience, especially for a service like DoorDash, where customers expect to know when their food will arrive. The main purpose of this project is to examine the relationship between order, market, and store-related information, and DoorDash delivery duration, with the aim of estimating the outcome using four machine learning models. By considering these factors together, the team hopes to better understand what affects delivery duration, whether machine learning can help produce more accurate estimates, manage customer expectations, and improve the general customer experience. 

# Contributions

- Julia Gonzalez: Problem statement, Model 1 and 2, modeling results and findings, discussion and conclusion, executive brief, executive presentation 
- Caly Nguyen: Model 3 and 4, modeling results and findings, discussion and conclusion, executive brief, executive presentation 
- Aishwarya Kuduvalli: Problem statement, data description, data pre-processing, EDA, final model evaluation, discussion and conclusion, executive brief, executive presentation

# Methods Used 

- Data cleaning
- Pre-processing
- Feature engineering and extraction
- Predictive modeling
- Machine learning
- Hyperparameter tuning
- Feature importance 
- Model performance evaluation and selection

# Technologies 

- Python
- Jupyter Notebook
- Visual Studio Code
- pandas, numpy, matplotlib, seaborn, scikit-learn, xgboost

# Project Description

The DoorDash ETA prediction dataset consists of 197,428 delivery records from 2015. It describes order details and times, store features, market information, and other correlated estimations, and is sourced from Kaggle. There are a total of 16 variables, and a response variable `delivery_duration` is created representing the time from when the order was created to actual delivery time in minutes.

## Questions and methods: 

Questions explored include the extent to which DoorDash delivery duration can be accurately estimated, what machine learning methods perform best in this regard, and what variables contribute the most to delivery duration. The analysis involved: 

- Preparing the data for modelling (cleaning, addressing missing values and outliers, encoding categorical variables)
- Exploring distributions, relationships to delivery duration, and correlated features 
- Partitioning the data using a 60/20/20 train-validation-test-split 
- Developing Linear Regression, XGBoost, Random Forest, and Histogram Gradient Boosting models
- Hyperparameter tuning
- Evaluating with mean absolute error (MAE), root mean squared error (RMSE), R², and bias
- Determining feature importance 
- Selecting and evaluation a final model on the test set 

# License

[MIT](https://www.mit.edu/~amini/LICENSE.md)

# Acknowledgements

- ADS-505: Data Science for Business, University of San Diego
- Kaggle - Doordash ETA Prediction Dataset
