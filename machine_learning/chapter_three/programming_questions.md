Question 1.

Interpretting precision, recall, f1 score and other metrics.

Steps:

1. Download this dataset: https://www.kaggle.com/mlg-ulb/creditcardfraud
2. split into test and train
3. train a classifier of your choosing
4. print out the classification report comparing the test sets ground truth against your predictions
5. interpret the results in terms of precision, recall and f1 score
6. Now rerun the classifier with StratifiedShuffleSplit from scikit-learn - do your results change? Why or why not?
7. Now use a logistic regression.  You may use any solver but do not set class_weight.  Report the statistics you get.  Why do you think you get this mix of precision, recall and f1 score?
8. Now use a logistic regression with class_weight="balanced".  Report the statistics you get.  Interpret your results.
9. Now add smote.  Please use this implementation: https://imbalanced-learn.readthedocs.io/en/stable/generated/imblearn.over_sampling.SMOTE.html - does this change anything?  Why or why not?
10. Now try the following example in your pipeline: https://imbalanced-learn.readthedocs.io/en/stable/auto_examples/pipeline/plot_pipeline_classification.html#sphx-glr-auto-examples-pipeline-plot-pipeline-classification-py does it perform any differently?  Why or why not? Report your metrics.
11. Throughout this analysis, you shouldn't have done particularly well.  Why do you think this is the case?  Is all hope lost?
12. Next try an Isolation forest.  You can find the documentation here: https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.IsolationForest.html Report your precision, recall, f1 score.  Note you should use train_test_split like this `train, test = train_test_split(df, test_size=.2)`
13. Last but not least, implement this blog post: https://towardsdatascience.com/outlier-detection-with-one-class-svms-5403a1a1878c making use of one class SVM.  Report your precision, recall and f1 score.
