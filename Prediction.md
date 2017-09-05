# Analysis and Prediction on HAR Dataset



##Background
Using devices such as Jawbone Up, Nike FuelBand, and Fitbit it is now possible to collect a large amount of data about personal activity relatively inexpensively. These type of devices are part of the quantified self movement – a group of enthusiasts who take measurements about themselves regularly to improve their health, to find patterns in their behavior, or because they are tech geeks. One thing that people regularly do is quantify how much of a particular activity they do, but they rarely quantify how well they do it.In this project, our goal will be to use data from accelerometers on the belt, forearm, arm, and dumbell of 6 participants. They were asked to perform barbell lifts correctly and incorrectly in 5 different ways. More information is available from the website here: http://groupware.les.inf.puc-rio.br/har (see the section on the Weight Lifting Exercise Dataset).

##Summary
The goal is to predict the manner in which they did the exercise by using the “classe” variable in the training set. We might also use any of the other variables to predict with. During the process we would be creating a report describing how we built model, how cross validation is used, what we think the expected out of sample error is, and why we made the choices you did. We will also use our prediction model to predict 20 different test cases.

##Data Preperation 

```
## Loading required package: lattice
```

```
## Loading required package: ggplot2
```

```
## [1] 19622    54
```

```
## [1] 20 54
```




## Build Machine Learning Models
### Decision Tree

```
## Rattle: A free graphical interface for data mining with R.
## Version 4.1.0 Copyright (c) 2006-2015 Togaware Pty Ltd.
## Type 'rattle()' to shake, rattle, and roll your data.
```

![](Prediction_files/figure-html/unnamed-chunk-2-1.png)<!-- -->


```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1471  165   42   46   50
##          B   52  737   83   78  108
##          C   17   70  801  146   85
##          D   92  131   69  644  102
##          E   42   36   31   50  737
## 
## Overall Statistics
##                                          
##                Accuracy : 0.746          
##                  95% CI : (0.7346, 0.757)
##     No Information Rate : 0.2845         
##     P-Value [Acc > NIR] : < 2.2e-16      
##                                          
##                   Kappa : 0.6782         
##  Mcnemar's Test P-Value : < 2.2e-16      
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            0.8787   0.6471   0.7807   0.6680   0.6811
## Specificity            0.9280   0.9324   0.9346   0.9199   0.9669
## Pos Pred Value         0.8292   0.6966   0.7158   0.6204   0.8225
## Neg Pred Value         0.9506   0.9167   0.9528   0.9340   0.9308
## Prevalence             0.2845   0.1935   0.1743   0.1638   0.1839
## Detection Rate         0.2500   0.1252   0.1361   0.1094   0.1252
## Detection Prevalence   0.3014   0.1798   0.1901   0.1764   0.1523
## Balanced Accuracy      0.9034   0.7897   0.8576   0.7940   0.8240
```

Decision Tree Model is predicting with 73.03% accuracy and 26.97% error rate.

### Random Forest Model

```
## randomForest 4.6-12
```

```
## Type rfNews() to see new features/changes/bug fixes.
```

```
## 
## Attaching package: 'randomForest'
```

```
## The following object is masked from 'package:ggplot2':
## 
##     margin
```

```
## Confusion Matrix and Statistics
## 
##           Reference
## Prediction    A    B    C    D    E
##          A 1674    1    0    0    0
##          B    0 1138    4    0    0
##          C    0    0 1020    4    0
##          D    0    0    2  960    0
##          E    0    0    0    0 1082
## 
## Overall Statistics
##                                           
##                Accuracy : 0.9981          
##                  95% CI : (0.9967, 0.9991)
##     No Information Rate : 0.2845          
##     P-Value [Acc > NIR] : < 2.2e-16       
##                                           
##                   Kappa : 0.9976          
##  Mcnemar's Test P-Value : NA              
## 
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            1.0000   0.9991   0.9942   0.9959   1.0000
## Specificity            0.9998   0.9992   0.9992   0.9996   1.0000
## Pos Pred Value         0.9994   0.9965   0.9961   0.9979   1.0000
## Neg Pred Value         1.0000   0.9998   0.9988   0.9992   1.0000
## Prevalence             0.2845   0.1935   0.1743   0.1638   0.1839
## Detection Rate         0.2845   0.1934   0.1733   0.1631   0.1839
## Detection Prevalence   0.2846   0.1941   0.1740   0.1635   0.1839
## Balanced Accuracy      0.9999   0.9991   0.9967   0.9977   1.0000
```
Random Forrest Model is predicting with 99.76% accuracy and 0.24% error rate.

##Conclusion
Random Forest model gives better predection (99.76%) over Decission Tree model (73.03%). so, appying Random Forest model on test data.

##Predictions

```
##  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 
##  B  A  B  A  A  E  D  B  A  A  B  C  B  A  E  E  A  B  B  B 
## Levels: A B C D E
```
