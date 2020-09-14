# Supervised-Machine-Learning-Credit-Risk
Presents a cohesive written analysis that:
✓ Describes the precision and recall scores.
✓ Describes the balanced accuracy score.
✓ Includes a final recommendation on the model to use, if any.
✓ Provides justification for your recommendation.

## Oversampling

## Naive Random Oversampling
```
array([[   72,    29],
       [ 7062, 10042]])
```

Calculated the balanced accuracy score
0.6499927062397539


Imbalanced classification report
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.71      0.59      0.02      0.65      0.42       101
          1       1.00      0.59      0.71      0.74      0.65      0.41     17104

avg / total       0.99      0.59      0.71      0.73      0.65      0.41     17205
```

## SMOTE Oversampling
```
array([[   64,    37],
       [ 5442, 11662]])
```
Calculated the balanced accuracy score
0.6577460891552205

Imbalanced classification report
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.63      0.68      0.02      0.66      0.43       101
          1       1.00      0.68      0.63      0.81      0.66      0.43     17104

avg / total       0.99      0.68      0.63      0.81      0.66      0.43     17205
```

## Undersampling
```
array([[   71,    30],
       [10385,  6719]])
```
Calculated the balanced accuracy score
0.6577460891552205

Imbalanced classification report
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.70      0.39      0.01      0.53      0.28       101
          1       1.00      0.39      0.70      0.56      0.53      0.27     17104

avg / total       0.99      0.39      0.70      0.56      0.53      0.27     17205
```
### Combination (Over and Under) Sampling
```
array([[   74,    27],
       [ 7077, 10027]])
```
Calculated the balanced accuracy score
0.5479011915457215

Imbalanced classification report
```
                   pre       rec       spe        f1       geo       iba       sup

          0       0.01      0.73      0.59      0.02      0.66      0.44       101
          1       1.00      0.59      0.73      0.74      0.66      0.42     17104

avg / total       0.99      0.59      0.73      0.73      0.66      0.42     17205
```





