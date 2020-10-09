
# week3



#### Metrics Motivation

* Why there are so many metrics?
  * Different metrics for different problems

* Why should we care about metric in competitions?
  * It is how the competotors are ranked

#### MAE vs MSE

* Do you have outliers in the data?
  * Use MAE

* Are you sure they are outliers?
  * USe MAE

* Or they are just unexpected values we should still care about?
  * Use MSE

#### Discussed the following metrics:

* MSE, RMSE, R-squared 
  * They are the same from optimization perspective

* MAE
  * Robust to outliers

#### DIscussed the metrics, sensitive to relative errors:

* MSPE
  * Weighted version of MSE
* MAPE
  * Weighted version of MAE
* MSLE
  * MSE in log space

### Classification metrics

##### Area Under Curve(AUC ROC)

![](./_image/2020-10-05-13-29-27.jpg)

* Best constant - All constants give same score
* Random predictions lead to AUC = 0.5


