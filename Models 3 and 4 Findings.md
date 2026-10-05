# Models 3 and 4 Findings

## Purpose

This notebook compares two tree-based regression models that predict DoorDash
delivery duration in minutes. It uses the train, validation, and test files
exported by the team's EDA notebook. The models do not repeat the EDA or create
a new data split.

## Model choice

Model 3 is a Random Forest. Model 4 is Histogram Gradient Boosting with
absolute-error loss. Both can capture nonlinear relationships, such as a busy
store having a different effect when the number of on-shift dashers is low.
The notebook uses a small three-fold `GridSearchCV` search on the training data
to keep the process readable and reproducible.

## Results from the verified run

Gradient Boosting was selected using validation MAE, before looking at the test
set. It had a validation MAE of **10.40 minutes**, compared with **10.87
minutes** for Random Forest and **13.33 minutes** for the median baseline.

On the held-out test set, Gradient Boosting had an MAE of **10.42 minutes**.
Random Forest had an MAE of **10.84 minutes**, and the median baseline had an
MAE of **13.29 minutes**. The selected model reduced average absolute error by
**21.6%** relative to the baseline. Its test RMSE was 15.10 minutes and its
test R-squared was 0.317.

The most useful validation features for the selected model were
`total_outstanding_orders`, `total_onshift_dashers`, and
`estimated_store_to_consumer_driving_duration`. These are predictive
associations, not proof that changing one feature will cause a delivery to be
faster or slower.

## Interpretation and limitation

The model is useful because it improves substantially on always predicting the
typical delivery duration. It still has meaningful errors: the selected model
underpredicted by about 2.5 minutes on average in this test set. The team split
is random, so these results estimate performance on similar historical orders.
A stronger final check would use a later time period as the test set to measure
how well the model holds up when operations change.

## How to run

Keep `training.csv` (or `train.csv`), `validation.csv`, and `test.csv` in the
project folder, then run `ADS 505 Final Project - Models 3 and 4.ipynb` from top
to bottom. The notebook writes its result tables to `results/`.
