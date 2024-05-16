# Mobile Plan Recommendation System

## Introduction

Mobile carrier Megaline has identified that many of their subscribers are still using legacy plans. To encourage the adoption of their newer plans, Megaline wants to develop a machine learning model that can analyze subscribers' behavior and recommend one of the new plans: Smart or Ultra.

The primary objective is to create a classification model that can accurately recommend the appropriate plan based on user behavior data. This project utilizes behavioral data from subscribers who have already switched to the new plans. The model should achieve the highest possible accuracy, with a minimum threshold of 75%. The final model's performance will be evaluated using a test dataset.

This notebook will explore and test three different machine learning models (DecisionTreeClassifier, RandomForestClassifier, and LogisticRegression) with varying hyperparameters to determine the best model that meets Megaline's requirements.  