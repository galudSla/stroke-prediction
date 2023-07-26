# Stroke Prediction

This repository contains the code and data for a data science project focused on predicting stroke occurrences in patients. The project involves data preprocessing, handling missing values, and employing a Random Forest classifier to predict stroke outcomes. The project utilizes various data attributes, including age, gender, hypertension, heart disease, average glucose level, and smoking status, among others, to make predictions.

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Data Preprocessing](#data-preprocessing)
- [Model Training](#model-training)
- [Evaluation Metrics](#evaluation-metrics)
- [Authors](#authors)

## Introduction
Stroke is a serious medical condition that requires prompt diagnosis and treatment. Predicting the likelihood of stroke can significantly aid in early intervention and potentially prevent severe consequences. This data science project aims to build a predictive model to determine whether a patient is at risk of experiencing a stroke based on various features from their medical records.

## Dataset
The dataset used in this project contains the following attributes:

1) `id`: unique identifier
2) `gender`: gender of the patient ("Male", "Female", or "Other")
3) `age`: age of the patient
4) `hypertension`: binary feature indicating the presence of hypertension (0: no hypertension, 1: hypertension)
5) `heart_disease`: binary feature indicating the presence of any heart diseases (0: no heart disease, 1: heart disease)
6) `ever_married`: marital status of the patient ("No" or "Yes")
7) `work_type`: type of work ("children", "Govt_job", "Never_worked", "Private", or "Self-employed")
8) `Residence_type`: type of residence ("Rural" or "Urban")
9) `avg_glucose_level`: average glucose level in blood
10) `bmi`: body mass index (Note: Rows with missing values for BMI were initially dropped in the preprocessing)
11) `smoking_status`: smoking status of the patient ("formerly smoked", "never smoked", "smokes", or "Unknown"*)
12) `stroke`: binary target feature indicating whether the patient had a stroke (1: stroke occurred, 0: no stroke)

*Note: "Unknown" in `smoking_status` means that the information is unavailable for this patient.

## Data Preprocessing
The data preprocessing steps performed in this project are as follows:

1) Dropped the 'bmi' column (`column_drop.ipynb`): The 'bmi' column contained NaN (Not a Number) values for some entries, which could not be used for analysis. Hence, the column was dropped from the dataset.

2) Imputation of missing values for 'bmi':
   - Replaced NaN values with the mean (`mean.ipynb`): Initially, missing 'bmi' values were replaced with the mean of the available 'bmi' values in the dataset.
   - Replaced NaN values with linear regression predictions (`linear_regression.ipynb`): Another approach was taken to impute missing 'bmi' values using linear regression based on other relevant features.
   - Used K-nearest neighbors (KNN) imputation (`kNN.ipynb`): Missing 'bmi' values were also imputed using KNN, which leverages the information from similar patients to fill in the missing values.

3) Encoding Categorical Data:
   - Label Encoding: When categorical data needed to be converted to numerical format, label encoding was applied to transform categorical values into numeric labels.
   - Manual Encoding: In some cases, manual encoding was used to map categorical values to specific numeric representations, ensuring the preservation of meaningful information.

## Model Training
The main goal of this project is to predict stroke outcomes using a Random Forest classifier. The following steps were performed for model training:

1) Data Splitting: The dataset was divided into a training set (75%) and a test set (25%) to train and evaluate the Random Forest classifier.

2) Random Forest Classifier: A Random Forest classifier was used due to its ability to handle non-linearity and feature interactions effectively. The model was trained using the training data.

3) Feature Importance: The feature importance scores were analyzed to understand the contributions of different features in predicting stroke occurrences.

## Evaluation Metrics
The performance of the Random Forest classifier was evaluated using the following metrics:

- F1 Score: The F1 score is the harmonic mean of precision and recall and provides a balanced measure of the model's accuracy.

- Precision: Precision is the proportion of true positive predictions (stroke cases correctly identified) out of all positive predictions made by the model.

- Recall: Recall, also known as sensitivity or true positive rate, is the proportion of true positive predictions out of all actual positive cases in the dataset.

## Conclusion
This data science project aimed to predict stroke occurrences in patients using a Random Forest classifier. The analysis involved data preprocessing to handle missing values, encoding categorical data, and feature engineering. The model's performance was evaluated using F1 score, precision, and recall metrics to assess its predictive capabilities.

The implementation code, dataset, and detailed analysis can be found in the respective project files within this repository.

## Authors

- [@galudSla](https://github.com/galudSla)
- email: tedgiann@gmail.com
