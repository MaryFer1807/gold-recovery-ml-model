# Gold Recovery Prediction – Industrial ML Project

## Project Overview
This project focuses on predicting **gold recovery efficiency** in an industrial mining process. The data comes from different stages of gold purification and includes both training and testing datasets with time-indexed features.

The main challenge is handling **missing features**, validating industrial formulas, and building a machine learning model evaluated with a **custom sMAPE metric**, commonly used in industrial optimization problems.

## Objective
The goals of this project are to:
- Validate the correctness of the gold recovery calculation.
- Analyze feature availability differences between training and test datasets.
- Explore metal concentration behavior across purification stages.
- Detect and remove anomalous process values.
- Train and evaluate machine learning models using a custom sMAPE metric.
- Predict recovery performance for unseen production data.

## Dataset
Three datasets are used:
- `gold_recovery_train.csv` – training dataset
- `gold_recovery_test.csv` – test dataset (no targets)
- `gold_recovery_full.csv` – full source dataset

The data is indexed by date and time, reflecting real industrial process measurements.

Target variables:
- `rougher.output.recovery`
- `final.output.recovery`

## Data Validation
- Verified the recovery calculation for `rougher.output.recovery` using the provided formula.
- Calculated the Mean Absolute Error (MAE) between computed and stored values to confirm correctness.
- Identified features present in the training dataset but absent in the test dataset.
- Analyzed feature types and availability constraints.

## Exploratory Data Analysis
- Studied changes in metal concentrations (Au, Ag, Pb) across purification stages.
- Compared particle size distributions between training and test datasets.
- Analyzed total substance concentrations at different process stages.
- Identified and removed anomalous values that could negatively affect model performance.

## Preprocessing
- Selected consistent features available in both training and test datasets.
- Removed invalid or extreme values based on industrial logic.
- Prepared datasets for modeling without data leakage.

## Modeling Approach
- Implemented a custom function to calculate **sMAPE**.
- Trained multiple regression models.
- Evaluated models using cross-validation with the custom sMAPE metric.
- Selected the best-performing model.
- Evaluated final model performance on the test dataset.

## Evaluation Metric
The project uses **sMAPE (Symmetric Mean Absolute Percentage Error)** as the primary evaluation metric, following industry standards for recovery prediction tasks.

A weighted final sMAPE score was calculated using:
- Rougher recovery
- Final recovery

## Tools Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Custom evaluation metrics
- Jupyter Notebook

## Business Value
This project demonstrates the ability to:
- Work with real industrial process data.
- Validate mathematical formulas used in production systems.
- Handle missing and delayed measurements.
- Apply custom evaluation metrics.
- Build robust machine learning models for industrial optimization.

The analysis supports data-driven decision-making in mining and production environments where efficiency and accuracy are critical.
