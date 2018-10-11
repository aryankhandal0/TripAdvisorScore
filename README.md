# TripAdvisorScore
Analysis of https://archive.ics.uci.edu/ml/datasets/Las+Vegas+Strip data.

# Algorithm
As the data contains multiple category columns we should either convert the category columns to One Hot Encoding to use RandomForest or XGBoost or we can use a categorical boosting algorithm like CatBoost or LightGBM.​

I have used CatBoost algorithm with loss function - "MultiClass", evaluation metric - 'MathewCorrelationCoefficient' and AUC(Area under Curve) is being displayed for every class.

Used paramsearch||gridsearch to find the best parameter to fit in CatBoost.

# Mathew Correlation Coefficient and AUC Score
The MCC doesn't depend on which class is the positive one, which has the advantage over the F1 score to avoid incorrectly defining the positive class.

AUC Score for each class is 0.84797, 0.6551724, 0.73828125, 0.5693473, 0.7039800.

AUC score is good if >0.7 which is true for 3 classes and thus with this less amount of data this prediction is good.

# Feature Importances


# More tries
I tried CatBoostRegressor and it gave an MAPE of 0.2354 and MAE of 0.7123.

But as the problem is of Classification as predicting a 2.5 is not clear to be biased with 2 or 3.

Regression can help us visualise the error as we can see the output is deviating 0.7123 from the rating.

However, such a poor prediction performance points out to a limitation as bias occurs in the model, resulting in underpredicting low ratings and overpredicting high ratings. 
  
