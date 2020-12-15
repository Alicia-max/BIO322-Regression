# BIO322-Regression-Project1

To predict the perceived pleasantness of an odour based on some molecular features in a regression task

# Code style 
R version used for this project : R version 3.6.1 (2019-07-05)

# installation 

Plateform used : jupyler lab 

library used that need to be install : ggplot2, caret, leaps, tree, xgboost, Matrix

DataSet in a csv file : "training_data.csv"

# Organisation 

Presentation of the data set (pleasantness to be predicted in fuction of intensity and some molecular features). 

Cleaning of the data. 

Performance of multilinear regression : with forward regresstion,  Lasso L1 and L2 regularization and PCA. 

Performance of nonlinear methods : descision tree, prunned tree and boosting tree. 

# Tests 

All the methods are tested by computing the resulting MSE. 

The MSE is evaluated on a test set as the method are computed using the training set. 

# Reproduction of the results 

The methods implemented can be used to predict valence pleasantness using a dataset with the same predictors as in the initial file "training_data.csv". 
