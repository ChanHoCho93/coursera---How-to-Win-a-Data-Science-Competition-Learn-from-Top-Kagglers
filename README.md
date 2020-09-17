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

