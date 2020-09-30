# coursera---How-to-Win-a-Data-Science-Competition-Learn-from-Top-Kagglers

## Goals
###  this course is about getting the required knowledge and expertise to successfully participate in data science competitions. That's the goal.

### week1 
- Intro to competiions & Recap
- Feature preprocessing & extraction

#### checking list
 - How data analysis differs between competitions and real companies

 - Review of major machine learning models

 - What software and hardware you need

 - Which python library you usually use

 - How to preprocess these features and create new ones

  

### Feature preprocessing

#### Numeric features

* Scaling and Rank for numeric feature:

  * Tree-based models doesn't depend on them.

  * Non-tree-based models hugely depend on them.

* Most often used preprocessings are:

  * MinMaxScaler - to [0,1]

  * StadardScaler - to mean==0, std==1

  * Rank - sets spaces between sorted values to be equal

  * np.log(1+x) and np.sqrt(1+x)

* Feature generation is powered by:

  * Prior kenowledge
  * Exploratory data analysis.

#### Categorical features

* Values in ordinal features are sorted in some meaningful order
* Label encoding maps categories to numbers
* Frequency encoding maps categories to their frequences
* Label and Frequency encodings are often used for tree-based models
* One-hot encoding is often used for non-tree-based models
* Interactions of categorical freatures can help linear models and KNN

#### Datetime features

* Periodicity

* Time since row-independent/dependent event

* Difference between dates

  

#### Coordinates features

* Interesting places from train/test data or additional data
* Centers of clusters
* Aggregated statistics

#### Handing missing features

* The choice of method to fill NaN depends on the situation
* Usual way to ddeal with missing values is to replace them with -999,mean or median
* Missing values already can be replaced with something by organizers
* Binary feature "isnull" can be beneficial
* In general, avoid filling nans before feature generation
* Xgboost can handle NaN

#### Pipline of applying BOW(bag of words)

* Preprocessing:
  
* Lowercase, stemming, lemmatization, stopwords
  
* Ngrams can help to use local context

* Postprocessing: TFiDF

  

#### BOW and w2v comparison

* Bag of words
  * Very large vectors
  * Meaning of each value in vector is known

* Word2vec
  * Relatively small vectors
  * Values in vector can be interpreted only is some cases
  * The words with similar meaning often have similar embeddings

#### CNN Images

* Features can be extracted from different layers
* Careful choosing of pretrained network can help
* Finetuning allows to refine pretrained models
* Data augmentation can improve the model

### week2
 - EDA
 - Validation
 - Data leaks

#### EDA (Exploratory Data Analysis)

* With EDA we can:    
    * get comfortable with the data
    * find magic features
    * Do EDA first. Do not immediately dig into modeling.
 * Exploring anonymized data
    * Try To decode the features - Guess the true meaning of the feature
    
    * Each type needs its own preprocessing
    
      

#### Explore features

* Explore individual features
  	* Histogram
  	* Plot(index vs value)
  	* Statistics

* Explore feature relations

   * Pairs
     	* Scatter plot, Scatter matrix
     	* Corrplot

  * Groups

    * Corrplot + clustering

    * Plot(index vs feature statistics)

      

#### Dataset cleaning

* Constant features

* Duplicated features

* Duplicated rows

* Check if dataset is shuffled (for meaning)

  

#### Vaildation and overfitting

* Vaildation helps us evaluate a qualit of th model
* Vaildation helps us select the model which will perform best on the unseen data
* Underfitting refers to not capturing enough patterns in the data
* Generally, overfitting refers to 
  * capturing noize
  * capturing patterns which do not generalize to test data

* In competitions, overfitting refers to

  * low model's quality on test data, which was unexpected due to validation scores

    

#### Vaildation strategies

* There are three main vaildation strategies:
  * Holdout
    * Split train data into two parts: partA and partB
    * Fit the model on partA, predict for partB.
    * Use predictions for partB for etimation model quality. Find such hyper-parameters, that quality on partB is maximized.
  * KFold
    * Split train data into K folds
    * Iterate though each fold: retrain the model on all folds except current fold, predict for the current fold.
    * Use the predictons to calculate quality on each fold. Find such hyper-parameters, that quality on each fold is maximized. You can also estimate mean and variance of the loss. This is very helpful in ordet to understand significance of improvement.
  * LOO
    * Iterate over samples: retrain the model on all samples except current sample, predict for the current sample. You will need to retrain the model N times (if N is the number of samples in the dataset).
    * In the end you will get LOO predictions for every sample in the trainset and can calculate loss.

#### Data splitting strategies

* In most cases data is split by
  * Row number
  * Time
  * Id

* Logic of featre generation depends on the data splitting strategy
* Set up your validation to mimic the train/test split of the competition

#### Problems occurring during validation

##### Vaildation stage

* Causes of different scores and optimal parameters
  * Too little data
  * Too diverse anad inconsitent data

* We should do extensive validation
  * Average scores from different KFold splits
  * True model on one slpit, evaluate scroe on the other

##### Submission stage

* We can observe that:
  * LB score is consistently higher/lower that vaildation score
  * LB score is not correlated with valition score at all

* Causes of validation probelms:
  * too little data in public leaderboard
  * incorrect train/test split
  * different distributions in train and test

##### Conclusion

* If we have big dispersion of scores on validation stage, we should do extensive validation
  * Averge scores from different KFold splits
  * Tune model on one slpit, evaluate score on the other

* If submission's score do not match local validation score,
  * we should
    * Check if we ave too little data in public LB
    * Check if we overfitted
    * Check if we clhose correct slpittiong strategy
    * Check if train/test have different distibutions

* Expect LB shuffle because of 
  * Randomness
  * Little amount of data
  * Different public/private distributions

* Summary of Validation topic
  * Defined validation and its connection to overfitting
  * Described common validation strategies
  * Demonstrated major data splitting strategies
  * Analysed and learn how to tackle main validation problems

### week3



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