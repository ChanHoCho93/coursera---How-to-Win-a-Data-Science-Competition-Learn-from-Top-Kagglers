# Week4

# Hyperparameter Optimization

## Goal 

- List most important hyperparameters in major models; describe their impact
- Understand the hyperparameter tuning process in general
- Arrange hyperparameters by their importance

### Hyperparameter tuning

### <Plan for the lecture>

* Hyperparameter tuning in general
  1. General pipeline
  2. Manual and automatic tuning
  3. What should we understand about hyperparameter?

* Models, librares and hyperparameter optimization
  1. Tree-based models
     - GBDT: XGBoost, LightGBM, CatBoost
     - RandomForest/ExtraTrees
  2. Neural networks
     - Pytorch, Tensorflow, Keras
  3. Linear models
     - SVM, Logistic regression
     - Vowpal Wabbit, FTRL
  4. Factorization Machines(out of scope)
     - libFM, libFFM

### <How do we tune hyperparameters>

1. Select the most influential parameters
   - There are tons of parameters and we can't tune all of them
2. Understand, how exactly they influence the training
3. Tune them!
   - manually (change and examine)
   - Automatically (hyperopt, etc.)

- Hyperparameter optimization software:
  - Hyperopt, Scikit-optimize, Spearmint, GpyOpt, RoBO, SMAC3

### <Tips>

1. Don't spend. too much time tuning hyperparameters
   - Only if you don;t have any more ideas or you have spare computational resources

2. Be patient
   - It can take thousands of rounds for GBDT or nenural nets to fit

3. Average everything
   - Over random seed
   - Or over small deviations from optimal parameters
     - e,g, average max_depth=4,5,6 for an optimal 5

-----

### Tips and tricks

