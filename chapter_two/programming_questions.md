Please note the following dataset repositories:

* http://archive.ics.uci.edu/ml/
* https://www.kaggle.com/datasets
* https://registry.opendata.aws
* http://dataportals.org/
* http://opendatamonitor.eu/
* http://quandl.com/
* https://homl.info/9
* https://homl.info/10
* https://www.reddit.com/r/datasets

These will generally be useful, possibly in your day job and absolutely for side projects.  Coming across good data is hard to do!  Fortunately others have taken care of this for us!

Question 1. 

The following dataset was taken from the first dataset repository: http://archive.ics.uci.edu/ml/datasets/Adult

As the original task of the dataset lays out, the goal is try and classify whether or not an individual is likely to make more or less than 50K per year.  Carry out this task.  Try at least five different algorithms, report precision, recall and f1 score on a test set.

Please note:
* the continuous variable fnlwgt represents final weight, which is the number of units in the target population that the responding unit represents.

Steps:

1. dealing with missing values - do you drop those rows?  Or do you try to impute the missing data?  If so how?  Explain why you chose the strategy you did.

2. Split your data into a test and training set.

3. Try five different models.  For each model deciding how many features to keep and how many features to drop.  Make sure you can explain why you dropped the features you did and why you kept the features you kept.  Try running the model with and without the features you kept.  Report the test precision, recall and f1 score.

Hint: if you are using linear regression the t-test can tell you which features are useful. 
Hint: if you aren't using linear regression dimensionality reduction techniques like T-SNE and PCA are very useful.
Hint: try scaling the features

4. Now try cross validation on the whole data set for each of the five models with and without the selected features.  Does the feature selection lead to under or over fitting?  How do you know?

5. Compare and contrast which features you kept and which ones you dropped, based on the model.  Note: it may be the case that different features perform better with different models, so please explore keeping and dropping different features depending on the algorithm.  How does your choice of model and features effect under or overfitting?

5. Try regularizing each of your models, does the generalizability increase?  Decrease?  In which cases does each happen and why?  Please try this with all of your features and then with the reduced set of features.  Report your precision, recall and f1 score on the train and test set.  Next carry out cross validation.  Does regularization reduce under or overfitting?  Why or why not?  How does the space of features your metrics and your optimal regularization parameters?

Question 2. 

Your next task is to see if weather effects trading on the new york stock exchange.

Start with the following datasets:

Weather data:
https://registry.opendata.aws/noaa-ghcn/

Stock Exchange data:
https://finance.yahoo.com/quote/%5ENYA/history?ltr=1

Choose any 1 year segment to answer the question.

Steps:

1. Download a year of weather data
2. Download a year of stock exchange data
3. create the following set of variables, specifically for New York City:
* raining:	
	* 0 - wasn't raining
	* 1 - was raining
* rain intensity:
	* 0 -low
	* 1 - medium
	* 2 - high
* rain duration in hours
* snowing:
	* 0 - wasn't snowing
	* 1 - was snowing
* snow intensity:
	* 0 - low
	* 1 - medium
	* 2 - high
* snow duration in hours
* windy:
	* 0 - low
	* 1 - medium
	* 2 - high
* Market Open
* Market Close
* Market High
* Market Low
* Market Volume

Your goal is to predict the volatility in the market, that is the Market High - Market Low.  You can use any of the other variables as predictors.  And you should only predict for the given data.  You can use past days as indicators for the current day, but your dependent variable is the volatility today.

4. Carry out feature engineering and decide which variables to use of the ones you created.

Hint: try dimensionality reduction and feature selection here.

5. Create a training and test set for the data.

6. Try five different models using mean squared error, root mean squared error, and mean absolute error as metrics.  Report your metrics.  Then try cross validation with the above metrics.  Is there overfitting?  How do you know?

7. Why do you think certain models worked well and others not as well?  How might you improve the model?

8. Try using two years of data this time.  Does your models accuracy improve?  Why or why not?

9. Try adding another data source to your dataset.  Does this change anything?

3. Implement a function that takes in a parameter 'k' and returns the kth norm.  So this function returns a function.  This function should only be defined for k >= 1.  Please see https://en.wikipedia.org/wiki/Norm_(mathematics) for more details.

Steps:
1. Use this function to create norms with:
	* k = 0.5
	* k = 0
	* k = inf
	* k = 1
	* k = 2
	* k = 10

2. Apply each of these metrics to your model using the test set.  Interpret the results of each.  Now run cross validation with each metric.  Remember, you'll need to take the negative of these metrics for cross validation!

3. Which metrics are useful for evaluation of your models, which are not?  Why?

4. Explain the significance of k = 0.5, k = 0, and k = inf.  How do they differ in evaluation from k = 1, k = 2, k = 10?


Question 3. 

In the chapter two kinds of train test split are used - stratified shuffle split and train test split.  Define both of these.  When would you use one versus the other?  Should you always use one versus the other?  Come up with an example showing each case for two datasets - one that is balanced and one that is unbalanced (please use binary classification).  Which does better in each case?  Does it matter which one you used?  Why or why not?  Please be consistent and just use logistic regression with the same hyperparameters and random seed.

