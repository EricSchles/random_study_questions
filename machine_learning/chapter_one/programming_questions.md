Question 1. 

Getting started with regression - scikit-learn

Steps:

1. load the boston dataset
2. split the data into test and training data
3. train a linear regression model
4. report the mean squared error on the test set.
5. try to interpret the coefficients of the linear regression model
6. run an F-test on the model with the null hypothesis that all of the parameters are jointly zero, does the model have any value?
7. run a t-test on each of the model's parameters with the null hypothesis that each of the model's parameters is not different than zero.  Which of the coefficents have value?

Question 2. 

Trying out instance based learning

Steps:

1. load the boston dataset
2. split the data into test and training data
3. train a KNN regression model with the default number of neighbors. 
4. report the mean squared error on the test set
5. try decreasing the number of neighbors to 2 and then report the mean squared error on the train and test set.
6. try increasing the number of neighbors to the size of the training set and then report the mean squared error on the train and test set.
7. set up a train and test set and then set up a for loop adjusting the number of neighbors until you find the K neighbors that returns the minimum mean squared error.  What value of K is it?
8. rerun your train test split, this time with a different train and test split, then try running your for loop again.  Do you get the same value of K that minimizes the mean squared error?
9. try each of the algorithms for knn regressor:
* auto
* ball_tree
* kd_tree
* brute
with the train and test split you just created in example 8.  Does the optimal K stay the same for each of the algorithms?  Why or why not is this the case?
10. Compare the results of KNN with linear regression using the same train and test set.  Please use the KNN that was optimal.  Which does a better job?  Why do you think that is?  Is there a benefit to using linear regression regardless of how well it does?

 