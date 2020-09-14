# Supervised-Machine-Learning-Credit-Risk

Balanced accuracy is a metric that one can use when evaluating how good a binary classifier is.

Precision is the measure of how reliable a positive classification is. It is obtained by dividing the number of true positives (TP) by the number of all positives (i.e., the sum of true positives and false positives, or TP + FP). 

Recall is the ability of the classifier to find all the positive samples. It summarizes how well the positive class was predicted.

F1 score is the harmonic mean of precision and recall. 

## Oversampling

The idea is simple and intuitive: If one class has too few instances in the training set, we choose more instances from that class for training until it’s larger.

## Naive Random Oversampling

Random oversampling draws from existing observations.

### Confusion matrix
```
array([[   72,    29],
       [ 7062, 10042]])
```
### Calculated the balanced accuracy score
0.6499927062397539
The accuracy score is at around 65%.

### Imbalanced classification report

Precision is high for the minority class but very low for the majority class. Majority class has higher recall than minority, 0.71 vs. 0.59.
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.71      0.59      0.02      0.65      0.42       101
          1       1.00      0.59      0.71      0.74      0.65      0.41     17104

avg / total       0.99      0.59      0.71      0.73      0.65      0.41     17205
```

## SMOTE Oversampling

The synthetic minority oversampling technique (SMOTE) is another oversampling approach to deal with unbalanced datasets. In SMOTE, like random oversampling, the size of the minority is increased, increased by interpolation.

### Confusion matrix
```
array([[   64,    37],
       [ 5442, 11662]])
```
### Calculated the balanced accuracy score
0.6577460891552205
The accuracy score is at around 66%.

### Imbalanced classification report
Precision is high for the minority class but very low for the majority class.
The recall metrics for minority is slightly imporved but slightly decreased for majority class.
It’s important to note that although SMOTE reduces the risk of oversampling, it does not always outperform random oversampling. Another deficiency of SMOTE is its vulnerability to outliers.
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.63      0.68      0.02      0.66      0.43       101
          1       1.00      0.68      0.63      0.81      0.66      0.43     17104

avg / total       0.99      0.68      0.63      0.81      0.66      0.43     17205
```

## Undersampling

Undersampling is another technique to address class imbalance. Undersampling takes the opposite approach of oversampling. Instead of increasing the number of the minority class, the size of the majority class is decreased.

### Confusion matrix
```
array([[   71,    30],
       [10385,  6719]])
```
### Calculated the balanced accuracy score
0.6577460891552205
The balanced accuracy score is at around 66%.

### Imbalanced classification report
Precision is high for the minority class but very low for the majority class. Recall metrics are better for majority class.
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.70      0.39      0.01      0.53      0.28       101
          1       1.00      0.39      0.70      0.56      0.53      0.27     17104

avg / total       0.99      0.39      0.70      0.56      0.53      0.27     17205
```

## Combination (Over and Under) Sampling

SMOTEENN combines the SMOTE and Edited Nearest Neighbors (ENN) algorithms. SMOTEENN is a two-step process:

- Oversample the minority class with SMOTE.
- Clean the resulting data with an undersampling strategy. If the two nearest neighbors of a data point belong to two different classes, that data point is dropped.

### Confusion matrix
```
array([[   74,    27],
       [ 7077, 10027]])
```
### Calculated the balanced accuracy score
0.5479011915457215
The balanced accuracy score is at around 55%.

### Imbalanced classification report
Precision is high for the minority class but very low for the majority class. Recall metrics are higher for majority class.
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.73      0.59      0.02      0.66      0.44       101
          1       1.00      0.59      0.73      0.74      0.66      0.42     17104

avg / total       0.99      0.59      0.73      0.73      0.66      0.42     17205
```

## Summary

All models have precision of 99%, they differ in recall and F1 score. Overall the best metrics has SMOTE Oversampling. Accuracy score for SMOTE of 66% was one of the highest scores measured.

```
                        pre       rec       spe        f1       geo       iba       sup
 
Random avg/total       0.99      0.59      0.71      0.73      0.65      0.41     17205
SMOTE  avg/total       0.99      0.68      0.63      0.81      0.66      0.43     17205
Under. avg/total       0.99      0.39      0.70      0.56      0.53      0.27     17205
Comb.  avg/total       0.99      0.59      0.73      0.73      0.66      0.42     17205
```
```
                       Calculated the balanced accuracy scores:
RandomOverSampler      65% 
SMOTE                  66% 
Undersample            66%
Combination            55%
```