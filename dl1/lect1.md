# Lecture One : Recognizing Cats and Dogs



## Time line wise notes

### 00 - 10 mins

- This course (Practical deep learning for coders) is about 
  - Getting up and running with deep learning in practie
  - Getting world class results
  - Focused on coding
- Lets go ahead and train a neural network!
- How to setup a server for GPU access.
- Jupyter notebook is third most important tool in field on data science.
- Crestle is good option to access AWS gpu enabled server.
- Paperspace is another great option.
- Go through set by step process of setting up server on paper space

### 10 - 20 mins

- Configure the server for fastai library along with cuda etc
- Python3 is mandatory, python2.7 is on verg of being absolute

### 20 - 30 mins

- We see only in 3 epochs training of a pre-trained model gets accuracy that is state-of-art
- About the implementation, there are two primary objects we deal with, one is data and other is model.
- FastAI uses pytorch at the backend.
- Look at the predictions :
  - Correctly labeled
  - Confidently labeled wrong class  

- Image aspect ratio is consern we should be aware of.

### 30 - 40 mins

- We just used a pre-trained model on Imagenet data to transfer learn on cat vs dog task

- But we cannot do the same for medical images like CT can etc.

- Top-down approach discussion

- Course structure : 
  - CNN image intro
  - Stuctured neural net intro
  - Language RNN intro
  - Collaborative filtering intro
  - Collaborative filtering in depth
  - Structured neural net in depth
  - CNN image in depth
  - Language RNN in depth

- Theme for today is how to build a image classifier

- Plan is to learn . . 

  - How to build a image classifier with minimum coding 
  - How to look at different kinds of images, like satelite images for multilable classification problem
  - How to deal with table data for sales forecasting
  - How to look at language and try to gigure out what does the text mean
  - Collabrative filtering for movie recommendation using imdb database
  - Text generation using neural network
  - How to build a object detection for images using heat map
  - How to write our own architecture from scratch

- Spend more and more time on coding than theory or research.


### 40 - 50 mins

- Bottom up approach works and it is proven to work.
- Googles's Alpha Go learns how classify a good board and bad board by reading images of boards.
- Traditional ML was very much domain knowledge dependent, hence development was very slow and costly.
- Deep learning (class of algorithms that work on neural network) is more generic in nature.

### 50 - 60 mins

- GPU are key in dealing with neural network
- Deep learning is been used in every part of buisness of google
- Deep learning is also been very effective in medical images to detect cancer at early stage.
- Popular examples of deep learning :
  - Fraud detection
  - Sales forecasting
  - Product failure prediction
  - Pricing
  - Credit risk
  - Customer retention / churn
  - Recommendation system
  - Ad optimizaion
  - Anit-money laundering
  - Resume screening
  - Sales prioritization
  - Call center routing
  - Store layout
  - Store location optimization
  - Staff scheduling

### 60 - 70 mins

- Human face decomposition using a nxn kernel's convolution.
- Non-linerar function follows convolution operation.
- Intuition behind gradient descent algorithm.
- Visualization and Understanding convolution

### 70 - 85 mins

- Visualization shows that the layer 2 has feaures build by combining features on layer 1 and as we go further the features become less basic and more specific.
- Cyclical learning rate concept
- Try out the classifier with other dataset and observe the outcome.



## Conclusion

