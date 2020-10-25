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

----------------------

### Advanced features ll

#### Statistics and distance based features

### <More features>

* How many pages user visited
* Standard deviation of prices
* Most visited page
* Many, many more

### <Neighbors>

* Explicit group is not needed
* More flexible 
* Much harder to implement

#### Matrix factorizations

### <Notes about matrix Factorization>

* Can be apply only for some columns
* Can provide additional diversity 
  * Good for ensembles

* It is a lossy transformation. lt's efficiency defpends on:
  * Particular task
  * Number of latent factors - Usually 5-100

### <Implementation>

*  Several MF methods you can find in sklearn
* SVD and PCA
  * Standard tools for matrix Factorization

* TruncatedSVD
  * Works with sparse matrices

* Non-negative Matrix Factorization (NMF)
  * Ensures that all latent factors are non-negative
  * Good for counts-like data

### <Conclusion>

* Matrix Factorization is a very general approach for dimensionality reduction and feature extraction
* It can be applied for transforming categorical features into real-valued
* Many of tricks trick suitable for linear models can be useful for MF

#### Feature interactions

### <Practical Notes>

* We have a lot of possible interactions - N*N for N features.
  * Even more if use several types in interactions 

* Need to reduce it's number
  * Dimensionality reduction
  * Feature selection

#### <Interactions order>

* We looked at 2nd order interactions
* Such approach can be generalized for higher orders
* It is hard to do generation and selection automatically.
* Manual building of high-order interactions is some kind of art 

### <Conclusion>

* We looked at ways to build an interaction of categorical attributes
* Extended this approach to real-valued features
* Learn how to extract features via decision trees

### t-SNE

### <Practical Notes>

* Result heavily depends on hyper parameters (perplexity)
  * Good practice is to use several projections with different perplexities(5-100)

* Due to stochastic nature, tSNE provides different projections even for the same data hyperparams
  * Train and test should be projected together

* tSNE reuns for a long time with a big number of features
*  it is common to do dimensionality reduction begore projection.

### <Conclusion>

* tSNE is a great tool for visualization
* It can be used as feature as well
* Be careful with interpretation of results
* Try different perplexities