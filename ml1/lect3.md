# Lecture Two



## Time line wise notes

### 00 - 10 mins

- This leacture is going to discuss beyond building a model that predicts accurate values and learn how to interpretate your model to understand your model better.
- RF allows use to understand our data deeper and more quickly.
- Also we learn how to deal with large dataset, like the gorcery competition in kaggle.
- When should we prefer RF ==> almost always worth trying, for unstructured data like image or voice we can also try deep learning. Also we can try collabrative filtering approach when we need it.
- A bug in proc_df function, the mean of missing value in training should be used in test set, hence we need to pass those mean values while calling proc_df for test data.
- Also if a column wont have any missing value in test data and it has in train set the coolean column wont be present in test data hence there will be shape miss match.

### 10 - 20 mins

- Grocery Sales Forecasting : Explain the problem statement, this is a good practice to explain the problem of data science in detail along with what data we ave what is the exact challenge to overcome.
- Practice the art of explaining the proble, it is very important skill to have.
- Grocery Sales Forecasting : It has relational dataset, the database has star schema, we have one main central table and many other tables containing meta data. Wejoin the meta data table to central table.
- Python itself is not fast but most of the stuff we use in data science is written in c and is highly optimized.
- We can specify dtype and avoid unnessesary ram usage, i.e if a column is year we need not read is as float.

### 20 - 30 mins

- We can use shuf on  command line to randomly sample data from csv an look at it and set dtype at the time of reading it in pandas.
- 4 years old data is important but not at the time of filling missing value

### 30 - 40 mins

- Use profiler to spot bottleneck of any step that is taking too long to complete.
- It is very frustrating to code for data science problems because if you make mistake in your code most of the time you wont see and exception or error but your accuracy wont be as high as it should have been! so when you have a model with accuracy that is half of what it could be just because you made a mistake.

### 40 - 50 mins

- kaggle practice is very important to understand what all errors you are prone to and fix them when working on company project.
- External data like weather or holiday is very offen used.
- Some winners have used lots and lots of features to get good accuracy and some have almost used no feature engg but used deep learning to learn mappings and still came 3rd place!!
- If you dont have good validation set it is impossible to generate a good model. Hence we need a reliable validation set.
- Choose validation set that has linear relation ship between test erro and validation error. 

### 50 - 60 mins

- Interpretating machine learning!
- A bug in proc_df function the validation set should be sliced after sorting data by date.
- Remember to calculate missing value based calculations on whole data set and use the dictionary to experiment with subset od data.
- We will be less confident about a prediction if the std of prediction across different trees is high.
- There is no inbuild method hence we need to calculate variance in prediction on our own. It is not optimized hence very slow.

### 60 - 70 mins

- To optmize a process by running it in parallel across trees fastai library has a method called paralle_trees(m, fn_pointer)
-  Explore  features using grpahs and basic statistics.
- A ML driven EDA, for which values in a feature our predictions are less confidence.
- Feature importance bar graph : 
  - Build a RF as fast as I can
  - Plot the feature importance and check in given features which features matter.
  - Sort the features by importance score
  - Many times only some columns that matter and rest others are not at all important.

### 70 - 85 mins

- What to do with a feaure importance graph
  - Study about the fearures that are most important and try to understand why do they stand out as most important ones.
  - Many times we might be surprized with the results and learn some new insights.
  - keep features that have significant importance and create a new RF
  - RF wont change, but now the model is simpler and more explainable.
- When you remove reduntant columns you are removing possible collinearity between columns which is a good thing. Reason been two colinear columns share importance between each other and having only one of them makes the importance graph more clearer.
- How to figure out how important is a feature ==> randomly shuffle that feature column and check models performance, if the error shots up a lot then the feature is relly important.
- We can also remove the feature and retrain but that will be very slow. hence shuflling the column in test data and see the prediction is much faster as we dont retrain our model.  



## Conclusion

We want to learn insights about data by going through few trees abd there errors and understand the feature so that we can fix any bug in data.