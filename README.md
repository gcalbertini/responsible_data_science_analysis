# Technical Audit of an Automated Decision System: Fairness Analysis of Kaggle code from 2020 annual CDC survey data of 400k adults related to their health status 

Authors: Martin Keenan and Guillherme Albertini

## Data Description

The "Personal Key Indicators of Heart Disease" dataset[^1] was published by the CDC and collected from the Behavioral Risk Factor Surveillance System. This system conducts a health-related survey each year, gathering information from over 400,000 adults. The dataset includes eighteen features, such as a binary target variable indicating the presence of heart disease, as well as sensitive features like race, sex, and age. Additionally, it contains other features such as BMI and alcohol usage.

## Automated Decision System

The audited model was uploaded by Kaggle user Wessam Salah Walid[^2]. This model predicts the likelihood of heart disease in adults and is optimized for accuracy. The machine learning pipeline involves several steps: outlier removal and dropping of certain features ("Alcohol Drinking," "Physical Activity," "General Health," and "Sleep Time"). Wessam employs five machine learning models, namely Logistic Regression, K-Nearest Neighbors, Random Forest, AdaBoost, and XGBoost Classifier, utilizing the scikit-learn and XGBoost libraries. Various over- and under-sampling techniques are also experimented with. Finally, all models are combined into a hard-voting ensemble, which is used to make predictions about heart disease.

## Motivation

This particular ADS is of interest due to its potential impact on decisions regarding the treatment of heart disease. The primary focus of our audit is to assess the fairness of the ADS's outcomes across sensitive groups defined by race, age, and sex. We aim to investigate whether the machine learning pipeline mitigates or amplifies biases present in the data.

## Proposed Auditing Methods

Our audit will involve examining Wessam's data pipeline for technical bias using the mlinspect tool. We specifically aim to evaluate whether the removal of outliers and features affects sensitive groups. Additionally, we will assess the suitability of accuracy as the optimization metric and consider additional fairness metrics using the fairlearn and Aequitas packages. We also plan to provide insights into the explainability of the model using methods such as SHAP, which will be covered later in the course.

## References

[^1]: CDC Behavioral Risk Factor Surveillance System, "Personal Key Indicators of Heart Disease," 2020. Available at: [https://www.kaggle.com/datasets/kamilpytlak/personal-key-indicators-of-heart-disease?datasetId=1936563&sortBy=voteCount](https://www.kaggle.com/datasets/kamilpytlak/personal-key-indicators-of-heart-disease?datasetId=1936563&sortBy=voteCount)

[^2]: Wessam Salah Walid, "Heart Disease Prediction (EDA & Modelling)(Acc 95%)," 2022. Available at: [https://www.kaggle.com/code/wessamwalid/heart-disease-prediction-eda-modelling-acc-95](https://www.kaggle.com/code/wessamwalid/heart-disease-prediction-eda-modelling-acc-95)
