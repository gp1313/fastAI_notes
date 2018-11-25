# Lecture Two : Deep Dive into RF



## Time line wise notes

### 00 - 10 mins

- **Goals for next 2 - 3 lectures**
  - How do RF actually work
  - Pros and cons of RF
  - What to do when RF dont work properly
  - What can we tune to get better result
  - How to interpretate Rf predictions to deeply understand our data
- **FastAI library**
  - Collection of state-of-the art techniques in ml world
  - Works hand in hand with pandas and sklearn
  - How to use fastai in your own code
    - get a local copy
    - simulink to git cloned folder
- **Review the code we studied in lecture 1**
  - evaluation method for given kaggle dataset
  - get everything into numbers
    - Date columns decomposition (add_datepart)
    - convert strings into categories (train_cat for mapping and proc_df to get numbers)
    - handle missing values using proc_df
    - run RF and get r2 score of 0.98

### 10 - 20 mins

- **What is R2 score ?**

  - Measure how the model explains the variance in data!
  - Disect the formula to get intiution behind the R2 score
  - range of r2 score is -infinity to +1
  - it is ratio of how good your model is w.r.t a average estimate model

- **Overfitting and Underfitting**

  - Creating validation dataset is the most important thing in process of ml project development
  - The validation dataset should be representative of real life data expected in testing phase
  - Be carefull while spliting for validation set when you have time element in your data.


### 20 - 30 mins

- **Difference between validation set and test set ?**
  - Validation set is used for hyper parameter tunning
  - Model will overfit validation data hence actual performance should be evaluated on test dataset
  - A good machine learning practionar knows how to set parameters effectively to avoid overfitting.
- **Base model**
  - Write funtion to print result of models preformance
  - To keep things interactive (e.g to set hyper parameters) the compute time should be small enough

### 30 - 40 mins

- **Speed up things for fine tunning**
  - train on subset of data which is randomly sample 

- **Single tree**
  - set n_estimators to 1
  - draw_tree()
  - A tree consists of sequence of binary decisions / binary splits.
  - Darker the color of block for are samples to be averaged in that set / node.
  - Also notice the error for that node as you propogate from root to leaf
  - First step to create a tree is to find the first split.

### 40 - 50 mins

- **How to choose the first variable to split on ?**
  - The variable that we can split the data into two groups such that the two groups are heterogenious to each other and homogenious within them self.
  - We try all the possible values of that variable and split the data into two groups.
    -  We evaluate the split by calculating the weighted average mse of two groups it create  
- **Create Forest using statistical technique bagging**
  - Idea is to have a N models that are not correlated to each other 
  - We sample the data in N set and train N model to overfit them.
  - They will generate random errors on rest of the data, but if take average of them i.e average of random error is zero, hence if we take average of N model prediction the error made will cancel out each other and what will remain is truth. For this logic to work the errors generated should not be correlated with each other.

### 50 - 60 mins

- **Create Forest using statistical technique Bagging**
  - N models trained on N different random subset.
  - N crapy models which are not correlated to each other can be averaged to get a good model. Here the errors of N crapy models are not correlated because they are trained on N different random subsets, the random subset gives rise to random errors generated.
  - Error should be uncorrelated to each other. This is based on principle that average of random error is zero.
  - Sampling is done with replacement i.e the the N subsets are overlapping. (boot strapping)
  - Number of trees (n_estimators) is the first hyper-parameter we tune, we set n_estimators according to validation error.
  - We asses the similarity between data points in tree space, i.e which data points are grouped together if a tree splits them appart.
  - An ideal machine learning model is the one that finds accurate and usefull relationship between variables in traning data and generalizes that to validation data / test data.
  - Bagging : Each tree should be predictive ass musch as possible and the predictions should be uncorrelated as much as possible.
  - Recent research points towards a fact that it is more important to get more uncorrelated trees than get more accurate tree. 
  - Extrem randomize tree model 
  - Uncorrelated tree : somewhere between  unncorrelated tree and accurate tree.
  - For continious variable split point we try all the possible values to split!!



### 60 - 70 mins

- Average of target value at leaf node works really well, but research has tried using linear regressor or median as replacement also, but not widely used.
- Use the power of jupyter notebook and python, use prediction of each tree / estimators and calculate mean of those and check error by comparing it with it target value. 
- How to set number of trees as hyper parameter == > N should be as big as you have time to fit  and also to the point were the error seems to be decreasing.
- 20 -30 tree is good range to start.

### 70 - 80 mins

- Out-of-bag score (OOB score) : The data points that were not selected while creating subset to train a tree can be used as vaidation set to evaluate that trees performance.
- sklearn provides a separate method called oob_score to see the validation error.
- oob score can be used to perform grid search to set hyper parameter.
- set_rf_sample(n) function will bootstrap whole data to generate subsets of n data points. 
- oob score and set_rf_sample are not compatable  to each other.

### 80 - 90 mins

- Practical tips to train RF model
  - Run most of your models on smallest possible data points to avoid overfitting and iteratively train your model with different hyperparameters to get a good idea on what hyperparameters to use.
  - min_samples_leaf parameters restricts depth of tree.possible values [1, 3, 5, 10, 25] in some case you might need it to be in range of 1000 too.
  - max_features = 0.5, the less correlated are trees to each other the better, If every tree is going to split on same point the trees might end been very similar to each, this parameters stops the process of going through all splits points and rather go through randomly sample variables at each split point.
  - When you split on a variable you dont discard the variable you can use it again and again and again.

### 90 - 100 mins

- It is hard to screw-up with RF! RF works most of the datasets most of the time.
- Trees haves very high representation of complexity capacity
- 



## Conclusion

