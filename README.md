# Chicago Crashes Dataset

## Overview

The Chicago Crash dataset included a lot of information that was taken at an accident. Some of these features included the lighting condition at the scene, the crash type, weather conditions even the traffic way type at the scene.

## Business Problem

In the event of an accident, what factors affect the damage cost and where it falls between a certain range:
    
    1. Below $500
    2. Between $500 - $1500
    3. Above $1500

## Analysis
Due to the runtime as a factor, a sample of about 20% of the dataset was used to analyse and have an estimate.

### Models
1: Base model had the lowest score due to overfitting

                    precision    recall  f1-score   support
    $500 OR LESS       0.19      0.18      0.19       558
    $501 - $1,500      0.26      0.28      0.27      1162
    OVER $1,500        0.67      0.66      0.67      3080

        accuracy                           0.51      4800
        macro avg      0.38      0.37      0.37      4800
    weighted avg       0.52      0.51      0.52      4800

2: LogisticRegression performed the best after three tuning models to penalty: l2 and solver: liblinear

                    precision    recall  f1-score   support

    $500 OR LESS       0.55      0.15      0.23       558
    $501 - $1,500      0.35      0.03      0.05      1162
    OVER $1,500        0.66      0.97      0.78      3080

        accuracy                           0.65      4800
        macro avg      0.52      0.38      0.35      4800
    weighted avg       0.57      0.65      0.54      4800

3: DecisionTreeClassifier

                    precision    recall  f1-score   support

    $500 OR LESS       0.48      0.15      0.22       558
    $501 - $1,500      0.26      0.02      0.04      1162
    OVER $1,500        0.65      0.96      0.78      3080

        accuracy                           0.64      4800
        macro avg      0.46      0.38      0.35      4800
    weighted avg       0.54      0.64      0.53      4800



4: KNN

                precision    recall  f1-score   support

    $500 OR LESS    0.53      0.07      0.12       558
    $501 - $1,500   0.34      0.10      0.15      1162
    OVER $1,500     0.65      0.93      0.77      3080

        accuracy                        0.63      4800
    macro avg       0.51      0.37      0.35      4800
    weighted avg    0.56      0.63      0.54      4800




* Various models were used to predict which factors contribute to the damage cost. These include LogisticRegression, DecisionTreeClassifier and KNearestNeighbor.
* LogisticRegression performed better than the other two in accuracy prediction

## Conclusion
* A lot of details were missing in some of the accidents and these led to most being classified as costing above $1500. Proper documentation of the scene and factors will help impove the classification and give a much more accurate prediction