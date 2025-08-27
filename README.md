# Deposit_Signing_Prediction

## Task
Predict whether a client will subscribe to a term deposit based on their profile information.

## Work done
#### Data Preprocessing
- analysis of features to determine those relevant for predictions
- analysis of missing data
- encoding categorical features and transforming categorical features to numeric ones where applicable
- scaling numeric features

#### Modeling
4 models were used for prediction:
1. Logistic Regression
2. Decision Tree (including hyperparameter tuning)
3. kNN (including hyperparameter tuning using GridSearchCV method)
4. XGBoost (2 methods of hyperparameter tuning were used: RandomizedSearchCV and Hyperopt) 

## Results
| Model                | AUROC_train | AUROC_test |
|----------------------|-------------|------------|
| Logistic Regression  | 76%         | 77%        |
| Decision Tree        | 80%         | 80%        |
| kNN                  | 80%         | 80%        |
| XGBoost              | 81%         | 81%        |

## Best model
XGBoost showed the best result among other models: AUROC 81% both for training and test datasets. The most significant features are: emp.var.rate and euribor3m.

XGBoost is a machine learning algorithm that works by combining many small decision trees to make one strong predictor. Each tree looks at the client's features and makes a small guess. Then, XGBoost combines all these guesses and learns from its mistakes, improving the prediction step by step. The result is a model that can take a client’s information and estimate the probability that they will sign a term deposit.

## Further considerations
As indicated in the task description and visible in the data, there is a significant relationship between the target variable and the duration of the last contact (duration). Therefore, it could also be useful to try creating a model where duration is the target variable and examine which features have the strongest influence on it. This may provide additional insights on how to improve the original model.
