# House-Prices-Prediction
A [kaggel competition project](https://www.kaggle.com/c/house-prices-advanced-regression-techniques) of predict sales price for each house.
## Table of Content

1) Exploratory data analysis - Exploring Data structure and visualization of important attributes 
2) Data preprocessing - Data cleaning and feature engineering
3) Preparing data for modeling - Transform variables and removing outliers 
4) Modeling - Try different model strategies and fine-turn the final model
5) Conclusion 

## 1. Exploratory data analysis - Exploring Data structure and visualization of important variables

The first step is always to read the [data description](https://github.com/shanj0716/House-Prices-Prediction/blob/master/data/data_description.txt). We need to build a foundation of knowledge on the variables, so that we can make informed decisions. There are 1460 instances of training data and 1460 of test data. Total number of attributes equals 81(including ‘Id’ and ‘SalePrice’), of which 36 is numeric, 43 categorical. 19 attributes of training data and 33 attributes of test data have missing data. Then, we look at the target attributes ‘SalePrice’, analysis its distribution and do some transformation.
Next, we explore the correlations of quantitative attributes and visualize the important attributes. With categorical attributes, we check distribution of ‘SalePrice’ with respect to variable values and enumerate create dummy variable for each possible category. 

All the data provided by Kaggel can be found [here](https://github.com/shanj0716/House-Prices-Prediction/tree/master/data). Ipython notebook used can be found [here](https://github.com/shanj0716/House-Prices-Prediction/blob/master/notebook/exploratory_data_analysis.ipynb).

## 2. Data preprocessing - Data cleaning and feature engineering
Before we move action to training model, data processing is always required. We applied several types of methods here:
1) Cleaning data with dropping bad attributes or instances
2) Dealing with missing values.
3) Creation new features from existing ones
4) Data transform

Ipython notebook used can be found [here](https://github.com/shanj0716/House-Prices-Prediction/blob/master/notebook/data_preprocessing.ipynb).

## 3. Preparing data for modeling - Transform variables and removing outliers 
First of all, we need to center and scale the ‘true numeric’ variables, and created dummy variables for the categorical variables. Then, we choose Ridge and Elasicnet to find the outliers of the training data. After dropping these outliers, we transform variables again to get the final training data.
 
Ipython notebook used can be found [here](https://github.com/shanj0716/House-Prices-Prediction/blob/master/notebook/preparing_data_for_modeling.ipynb).

## 4. Modeling - Try different model strategies and fine-turn the final model
We try 9 wildly used regression model to train with our data, using GridSearch to optimize the parameters. Comparing single model with stacking models, we choose the best model to do prediction. Furthermore, we fine-turn the prediction values manually.

Ipython notebook used can be found [here](https://github.com/shanj0716/House-Prices-Prediction/blob/master/notebook/modeling.ipynb).

## 5. Conclusion 
With the final model, our prediction got a 0.117 RMSE score comparing with the real ‘Salesprice’ data.  However, Kaggel doesn’t publish the data, so we cannot do much more evaluation. All of all, housing price prediction is a typical regression problem, which can help us get a deeper understanding of the whole machine-learning process. Finally, here’s some thinking of this project:

1) As you can see, each of the models produces results that vary quite widely. Some models will be much better at catching certain signals in the data, whereas others may perform better in other situations. Using a combination of many different models is helpful to create a more generalized model, which is resistant to noise.

2) Only CV score is hardly to get a precise evaluation in the face of limited data, which can be heavily influenced by overfitting. 

3) With regression the smallest things can make a huge difference. Dealing with outliers (we did) and overfitting (we need to do) are both important for features engineering.
