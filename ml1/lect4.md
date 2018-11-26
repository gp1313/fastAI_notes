# Lecture Four



## Time line wise notes

### 00 - 20 mins

- Mege conflict in jupyter notebook ==> No real solution
- Summarize things discussed till now :
  - Hyperparameters of interest :
    - **set_rf_sample** : how many data points does each tree gets to train on. lets say this number is N, One cool way to know the N is large enough is by running the modeling i.e training and predicting multiple times if the performance is same for all the attempts the set_rf_Sample number is large enough.
    - **depth_of_tree** : max depth can be  ln2(N), high depth can cause overfitting. Ideally we need high accuracy of each estimator but also minmum correlation across trees is also needed.
    - **min_sample_leaf** : It  is another way to decrease or increase tree depth.
    - One condition when RF stops spliting is when all the data points in that group have identical dependent value (target value) because there is no split that can improve the accuracy from there. i.e no new information gain.
    - **max_features** : It determine how many features are considered (randomly sampled) while spliting the data. this results into uncorrelated trees after training.

### 20 - 30 mins

- If you want to use any method from fastai library you also copy the source code function you need to your code and mention github link for reference to other developers.
- feature import works by shuffling the column and recalculate prediction error.
- Tree based approach leverages interaction between variables in dataset which makes this approach very very effective because the way world works the real life data has many interaction.
- Having correlated features underestimates there importance.

### 30 - 40 mins

- Reasons why validation erro got worse after some feature engg :
  - Overfitting might be the reason, but in case of RF it is less likely.
  - If the validation set is not aliened with training set. Like the training set has some things that are not at all present in test set and vise versa.
-  Feature importance in industry v/s ml research community :
  -   General wron assumption is that the variables are linearly related. Hence the coefficients are used to derive feature importance (linear regression model) which is only correct if the the data preprocessed is at its truest form abd the model has not missed out on any variable interaction needed to model data. One should be very skeptical when cooefficients of linear regression model are interpretated for feature importance.

### 40 - 50 mins

- **One hot encoding** : it makes more sense and suits tree approach . Use max_n_cat for enabling it in fastai library.
- You should try one hot encoding not to boost accuracy but to get insights using feature importance.

### 50 - 60 mins

- Remove redundant features using cluster analysis.
- We try to find out which two features are most similar to each other.
- Rank correlation c\over comes non-linear correlation problem.

### 60 - 70 mins

- We look into groups that are very similar to each other by monitoring there oob score
- Remove one from each pair an retrain, the accuracy is same but our model is much simplar now.
- Visualize inter relationship between two features using bar plot and ggplot.

### 70 - 80 mins

- Use partial dependent plot and analyse the data to improve our understand.
- We replace feature column with a constant

### 80 - 90 mins

- Cluster analysis + partial differential plot to understand data.
- Limitation of these techniques.

### 90 - 100 mins

- Tree interpreter : It is useful to answer why / reason behind any prediction.
- We can see what features increase or decrease the prediction value.



## Conclusion

ML based EDA is very insightfull!