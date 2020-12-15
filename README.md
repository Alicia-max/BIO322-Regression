# BIO322-Regression-Project1
To predict the perceived pleasantness of an odour based on some molecular features in a regression task. 

# Code style 
R version used for this project : R version 3.6.1 (2019-07-05)

# Installation 
Plateform used : jupyler lab 

Library used that need to be install : ggplot2, caret, leaps, tree, xgboost, Matrix

DataSet in a csv file : "training_data.csv"

# Organisation 
Presentation of the data set (pleasantness to be predicted in fuction of intensity and some molecular features). 

Cleaning of the data. 

Performance of multilinear regression : with forward regresstion,  Lasso L1 and L2 regularization and PCA. 

Performance of nonlinear methods : descision tree, prunned tree and boosting tree. 

# Tests 

All the methods are tested by computing the resulting MSE. 

The MSE is evaluated on a test set as the method are computed using a training set. 

# Reproduction of the results 

The methods implemented can be used to predict valence pleasantness using a dataset with the same predictors as in the initial file "training_data.csv". 

**example : Predict valence pleasantness using the predictors of a given file (test_data) and the boosting tree method of this project, the results are written in a csv file:**


Data.prediction<- read.csv(file.path("..","data","test_data.csv"))

lookup <- c("low" = 1, "high" = 0)

Data.prediction$Intensity <- lookup[Data.prediction$Intensity]


Data<-Data.prediction[, colnames(Data.prediction)%in%colnames(plea.train.x)]

Data.x <- xgb.DMatrix( data.matrix(Data), missing = NA)
pred<-predict(boost.pleas, Data.x)

result<- data.frame('Id'=Data.prediction$Id, 'VALENCE.PLEASANTNESS' = pred)

result

write.csv(x=result, 'monprojet.csv', row.names = FALSE )


