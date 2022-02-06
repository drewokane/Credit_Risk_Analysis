# Credit Risk Analysis

## Purpose

The following analysis has been done to determine which of the following
models is best when determining credit risk of applicants. Given an input
of an applicants information, the model used will return whether or not the applicant is a credit risk.

To train and evaluate the models, we will be using a dataset consisting of credit applicants from Q1 2019. Six models will be evaluated on their
balanced accuracy scores, precision, and recall.

## Results

| Model | Balanced accuracy score | Precision (minority) | Recall (minority) |
|-------|:-------------------------:|-----------|--------|
|Logistic regression w/random oversampling| 0.61554 | 0.01 | 0.56 |
|Logistic regression w/SMOTE oversampling| 0.63693 | 0.01 | 0.62 |
|Logistic regression w/cluster centroids| 0.51987 | 0.00 | 0.56 |
|Logistic regression w/SMOTEENN sampling| 0.61851 | 0.01 | 0.66 |
|Balanced Random Forest Classifier| 0.83978 | 0.04 | 0.77 |
|Easy Ensemble AdaBoost Classifier| 0.92907 | 0.06 | 0.92 |

## Summary & Recommendations

In comparing all the models, we will not be looking at precision, for two
reasons. Firstly, all of the precision scores are roughly simliar and 
thus no model stands out. Secondly, the precision for the minority class 
was almost always around 1%, indicating that none of the models could 
correctly identify the minority class with great confidence.

There is a clear divide between the ensemble based methods and the 
sampling based methods. All the sampling based methods had balanced 
accuracy scores below 0.64, while the ensemble methods had scores above 0.
83. While this again does not necessarily mean something significant when 
we are dealing with imbalanced classes, accuracy is still important to 
have at the very least.

When looking at precision and recall, the ensemble based models really
stand out. While both had very low precision, both had higher recall 
scores. This means that of the applicants labeled as being in the 
minority class, most of them actually were of the minority class.

For the application of identifying credit risk applicants, it seems
best to make sure we are not being overzealous in labeling risky 
applicants and being sure of who we label. For this reason, I would recommend the Easy Ensemble AdaBoost model.
