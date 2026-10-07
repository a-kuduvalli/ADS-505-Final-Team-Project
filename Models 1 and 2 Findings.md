# Models 1 and 2 Findings

## Purpose

This analysis looks at how well Linear Regression and XGBoost can predict DoorDash delivery times. Using the same prepared datasets, we can compare their accuracy and see whether a more complex model offers a meaningful improvement over a simpler approach.

## Model choice

Linear Regression was chosen as a starting point because it provides a simple way to examine the relationship between order information and delivery duration. XGBoost was included to see whether capturing more complex patterns would improve prediction accuracy. Unlike Linear Regression, XGBoost required some tuning, so four configurations were compared using validation MAE. The model with a maximum tree depth of 8 performed best.

## Results from the verified run

XGBoost performed better than Linear Regression on both the validation and test datasets. During validation, XGBoost achieved an MAE of 10.47 minutes, compared with 11.31 minutes for Linear Regression.

The results remained consistent on the test set:

| Metric | Linear Regression | XGBoost |
|---|---:|---:|
| MAE | 11.38 minutes | 10.49 minutes |
| RMSE | 15.72 minutes | 14.68 minutes |
| R² | 0.260 | 0.355 |
| Bias | +0.20 minutes | +0.23 minutes |

Overall, XGBoost reduced average absolute prediction error by approximately 7.9% compared with Linear Regression. It also explained more variation in delivery duration, although neither model was able to account for all of the differences between orders.

Feature importance showed similar patterns across both models. Outstanding orders and dashers on shift were the strongest predictors, followed by estimated driving duration. One interesting difference was that order hour played a larger role in XGBoost, suggesting that the more complex model was able to use time-of-day information more effectively.

## Interpretation and limitation

The results suggest that XGBoost is the stronger choice between these two models, but there is still room for improvement. Both models struggled with unusually long deliveries, often predicting much shorter times than what actually occurred. This is worth considering if the predictions are eventually used to provide delivery estimates to customers.

Another limitation is that the team used a random data split rather than separating orders by date. While the similar validation and test results are encouraging, they don't necessarily tell us how well the models would perform on future orders. Testing with newer delivery data would provide a better picture of how reliable these predictions are over time.

## How to run

Keep `training.csv`, `validation.csv`, and `test.csv` in the main project folder. Run `ADS 505 Final Project - Models 1 and 2` from beginning to end. The notebook trains both models, evaluates their performance, and saves the validation results, test results, and feature importance scores in the shared `results/` folder.