# Learning Data Cleaning and Preprocessing with Python

## Overview
This repository documents my hands-on learning and practice of data cleaning and preprocessing using the **Pima Indians Diabetes Dataset**.

The goal was to understand how to explore a dataset, identify data quality issues, handle missing values, detect outliers, and prepare data using Python.

## Dataset
- **Dataset:** Pima Indians Diabetes Dataset
- **Source:** [Kaggle – Pima Indians Diabetes Database](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
- **Records:** 768
- **Features:** 8 input features and 1 target column (`Outcome`)

## Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Learning and Preprocessing Steps

### 1. Data Exploration
- Loaded the dataset using Pandas.
- Examined rows, columns, data types, and statistical summaries.
- Checked for missing values and duplicate records.

### 2. Handling Invalid Zero Values
Identified zero values that represented missing or invalid measurements in:
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI

Converted these values into NaN. Zero pregnancies were retained because they are valid.

### 3. Outlier Detection
Used the **Interquartile Range (IQR)** method to identify potential outliers in numerical columns.

### 4. Outlier Treatment
Applied **Winsorization** using the IQR lower and upper bounds to limit extreme values.

### 5. Missing Value Imputation
Used **KNN Imputation** from Scikit-learn to estimate missing numerical values.

- Number of neighbors: 5
- Weighting: Distance-based
- StandardScaler was used before KNN imputation.
- The target column (`Outcome`) was excluded from imputation.

### 6. Data Visualization
Used Matplotlib and Seaborn to visualize distributions and examine the effect of preprocessing.

## Files in This Repository

| File | Description |
|---|---|
| `diabetes_cleaning.ipynb` | Notebook containing the learning and preprocessing steps |
| `diabetes_dataset_postcleaning.csv` | Exported cleaned dataset |
| `README.md` | Documentation |

## Important Notes
- KNN imputation estimates missing values; it does not recover the original measurements.
- Winsorization changes extreme observations by limiting them to specified bounds.
- The preprocessing in this learning exercise was performed on the complete dataset. For predictive modelling, preprocessing steps should be fitted only on training data to avoid data leakage.

## Key Takeaways
Through this exercise, I gained hands-on experience with:
- Data exploration using Pandas.
- Identifying and handling invalid values.
- Understanding and treating outliers.
- Missing value imputation using KNN.
- Data visualization.
- Preparing datasets for future Machine Learning workflows.

**Learning by doing, one concept at a time.**
