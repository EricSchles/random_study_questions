In this assignment we will look at some typical image based machine learning tasks.

1. Image classification - this uses the whole image to classify what's happening
2. Object detection - this trying to detect an object within a broader image context
3. Image narration - this tries to make use of the detection of multiple objects to tell a story about the picture.

Question One - Image Classification

Download the data from this kaggle competition: https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia

Steps:

1. Read the data into a pandas dataframe

2. Normalize the data, this can mean greyscaling the data or normalization in some other capacity.

3. Resize the data to a standard size.  This should be X by X.  So for instance 224 by 224, where X = 224.

4. Train a thin model ontop of VGG16.  Use the VGG16 with imagenet weights.  Then set a few layers to trainable
towards the end of the network.  Report your precision, recall, f1 score, and print out a roc auc chart. This should
include a diagram of your models training performance, which you can get in the following way:

```
model_history = model.fit(X, y)
print(model_history.history)
```

Then use `classification_report` from scikit-learn and roc auc curve from yellowbrick: https://www.scikit-yb.org/en/latest/api/classifier/rocauc.html

Compare the results on train, test and validation.  How well did your classifier do?  Why do you think you got the results you did.

5. Rerun the above model, this time using cross validation: https://machinelearningmastery.com/evaluate-performance-deep-learning-models-keras/ 

Note: this means you will need to combine test, train and validation.

What does this tell you about the model?  Was there overfitting?

6. Now rerun the model with VGG16 and imagenet weights, except instead of retrainging some of the later layers in the network, you'll be adding new layers on the end of the network.  This tutorial can show you how to do that: https://www.pyimagesearch.com/2020/03/16/detecting-covid-19-in-x-ray-images-with-keras-tensorflow-and-deep-learning/

Report your model history, your results on test and validation, like before.  What changed?  Did your model do better?  Worse?  You should note that model size is directly related to under or overfitting.  Too few layers and nodes per layer and your model underfits, too many and it overfits.  Tie this notion to your analysis.  

7. Now rerun cross validation with your new network.  Does this confirm your belief of over or under fitting?

8. Now rerun your analysis with ResNet50, start by making the last few layers trainable.  Then set trainable to False and add new network layers.  Report your analysis like in the previous steps.  Did ResNet50 do better or worse than VGG16?  Why do you think this is the case? 

Question Two - Object Detection

Download the Common Objects in Context dataset (aka COCO): http://cocodataset.org/#home

You'll be carrying out the instance annotation task.  See the jupyter notebook here for context: https://github.com/cocodataset/cocoapi/blob/master/PythonAPI/pycocoDemo.ipynb

Your goal is to pick out the object in the image.

1. Read the data into memory
2. Generate a label set from the list or annotations, remember to choose the instance annotations!
3. Next make use of yolo to predict on the test set. This tutorial might be helpful: https://machinelearningmastery.com/how-to-perform-object-detection-with-yolov3-in-keras/ You'll need to take this tutorial and then fit it to a generic object detection context.  The tensorflow docs may be helpful as well: https://github.com/tensorflow/models/tree/master/research/object_detection  Please report your metrics for the test set.  You should make use of these metrics: https://github.com/rafaelpadilla/Object-Detection-Metrics here is an implementation: https://github.com/Cartucho/mAP
4. Next make use of Mask R-CNN to do object detection.  Please follow this tutorial: https://machinelearningmastery.com/how-to-train-an-object-detection-model-with-keras/ remember again, you'll need to generalize to finding any object.  Please report out your metrics as you did before.  
5. Compare and contrast YOLO and Mask R-CNN, which did better?  How did you decide that?  Does one model or the other do better on different kinds of labels?  If so, why do you think?
6. Now try OctConv: https://github.com/titu1994/keras-octconv, please report your metrics as in the last two examples.  Which one does the best?



