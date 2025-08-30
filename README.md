# DSN-2025-AI-Bootcamp-Qualification-Hackathon-Project-Participation
Used Car Price Prediction

This repository contains my solution for the Used Car Price Prediction challenge. The task is to build a predictive model that estimates the price of a car based on its features (brand, model, mileage, year, engine, etc.).

The workflow is designed to be clean, reproducible, and Colab-ready.

 Project Overview

Goal: Predict car prices as accurately as possible.

Data: Provided train and test datasets (train.csv and test.csv).

Target Variable: price

Submission Format: A CSV file with columns id and price.

 Approach
1. Data Loading

Loaded train and test datasets using pandas (on_bad_lines="skip" to handle corrupted rows).

2. Feature Engineering

Extracted structured features from the raw engine text (horsepower, liters, cylinders).

Derived new features:

car_age = 2025 - model_year

milage_per_year = milage / car_age

Cleaned categorical columns (fuel_type, accident, clean_title).

3. Encoding

Low-cardinality features: Encoded with LabelEncoder.

High-cardinality features (brand, model, colors, engine): Encoded with frequency encoding.

4. Model

Chosen model: HistGradientBoostingRegressor (scikit-learn)

Parameters:

max_iter=250

learning_rate=0.08

random_state=42

5. Training & Validation

Target: price

Features: All except id and price.

Missing values in numerical features filled with mean.

Validation RMSE is printed after training.

6. Prediction & Submission

Predicted car prices for the test set.

Saved results to submission.csv in the required format.

 How to Run

You can run the notebook directly in Google Colab:

# Open in Colab
!git clone <this-repo-link>
%cd <this-repo-name>

# Run script
!python main.py


Or open the notebook version (notebook.ipynb) in Colab and execute cell by cell.

 Results

Validation Metric: RMSE (Root Mean Squared Error).

Example output:

submission shape: (125690, 2)
Validation RMSE: XXXX


Submission file: submission.csv

📁 Repository Structure
.
├── train.csv              # Training dataset
├── test.csv               # Test dataset
├── main.py                # Training + prediction script
├── notebook.ipynb         # Colab-friendly notebook
├── submission.csv         # Generated predictions
└── README.md              # This file

 Requirements

Python 3.8+

pandas, numpy

scikit-learn

Install with:

pip install pandas numpy scikit-learn

 Notes

Simple but effective feature engineering + gradient boosting baseline.

Can be further improved with hyperparameter tuning, cross-validation, and advanced feature extraction.
