# Lecture One



## Time line wise notes

### 00 - 10 mins

- Use the forum to checkout info on what environment to use technology changes etc.
- We are going to be learning Machine Learning today!
- Set up your jupyter notebook
- install fastai library
- Get familiar with Jupyter notebook workflow
- Basic approach :
  -  Get straight into code
  - Theory comes later
  - Focus on experimenting with notebooks
  - The more coding you do more you learn about machine learning
- Stuff discussed here is Jeremy's work for past 25 years
- Examples of technical learning are provided and encourage
- autoreload commands help sync source code after change in external library
- PEP 8 code style is not followed, reason been data science is not software engg. 
- We are prototyping models, some of these models might get into productio hence will go under software engg later
- Best practice for prototyping model :
  - Doing things very interactively
  - Do things iteratively

### 10 - 20 mins

- Advantage of using interactive environment like Jupyter notebook
  - You can read defination any function of any library just by single key stroke
  - It is easy to understand implementation and it is very important in future
- Data for lesson one : Bulldozers using Kaggle
  - Predict auction sale price of heavy equipement
  - Kaggle : A platform that provides authentic experience of applied machine learning
  - On your own dataset the toughest question is to answer : "Is current accuracy the best possible number?"
- Machine learning should make you understand the dataset better
- Download the kaggle dataset on server using forefox and curl command

### 20 - 30 mins

- Get pointer to data and verify using "ls" command
- Structured data ==> data stored in tables
- import the data into pandas dataframe
- low memory = false helps to store type of columns while reading it.
- format string feature in python 3.6 ==> f'Hello {name}' ==> 'Hello Gaurav'

### 30 - 40 mins

- Explore the csv file using cool features of jupyter notebook
- We should prefer machine learning driven EDA to avoid any bias
- log scale of sales price is very important because we dont care about the actual magnitide or error but the percentage of error made by the model. 
- Take the log of sales values and replace it with original sales value (note : pandas series can be directly passed to numpy function)
- About Random Forest
  - Universal machine learning technique
  - Can classify or predict float value
  - Genrally does not overfit
  - Doesnt need validation set
  - It can tell how it generalize
  - It has very few if any statistical assumptions
  - Its a great place to start
- Curse of dimensionality and free lunch theorem is meaning less

### 40 - 50 mins

- KNN works really work well in high dimension.
- Imperical facts about Machine learning :
  - More the columns the better.
  - In real world dataset are not random, hence techniques that work are the one to focus on.
  - SKlearn : ml toolkit with very wide range of algorithms.
- Regression is any ml model that tries to predict  continous outcome.
- shift + tab ==> parameters
- ?function ==> source code
- Run random forest on loaded data and see it fail.
  - Everything has to be numbers
  - dtype of date column is 'datetime' we need int or floats
- Decompose the date into various columns

### 50 - 60 mins

- add_datepart() ==> read the source code (because it is a useful skill to have)
  - add all the plausible decomposition of date as we dont have to worry about number of columns
  - source code is prety readable
- In pandas data frame use square bracket to access columns it is safer than dot method
- convert columns with dtype strings into numbers using train_cats function
- Be careful of miss matching of categorial variable mapping in train set and test set.

### 60 - 70 mins

- feature format : The fastest way to save and load any file. It is becoming a universal standard
- proc_df function usage and sudo code
  - makes a copy of df
  - grab and drop the dependant variable
  - fix missing values
  - create boolean column with True when value is missing 
  - replace the categorial columns with its cat.codes
  - create dummy columns (not going to do for now)

### 70 - 80 mins

- output of proc_df is train ready
- RF are parallalizable, use your CPU core!!
- Get R2 score.
- Split data into separate validation dataset. (sort table by dates).



RF are insanely powerful and kaggle leader board is proof of that!