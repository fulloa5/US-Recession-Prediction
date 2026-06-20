# U.S. Recession Prediction Using Logistic Regression

## Project Overview

This project develops a logistic regression model to estimate the probability that the United States economy is in a recession using historical macroeconomic indicators.

The objective is to demonstrate an end-to-end data science workflow, including data preparation, exploratory data analysis, feature engineering, model development, interpretation, and evaluation.

Rather than treating logistic regression as a black-box model, this project explains the mathematical foundations behind the model while illustrating how economic indicators contribute to recession probability.

---

## Problem Statement

Economic recessions have significant impacts on businesses, investors, and policymakers. Identifying periods of elevated recession risk can support more informed decision-making.

This project explores whether commonly used macroeconomic indicators can be combined to estimate recession probabilities using logistic regression.

---

## Dataset

The project combines publicly available U.S. economic indicators at the monthly level.

Variables include:

* 10-Year Treasury Minus 3-Month Treasury Yield Spread
* Federal Funds Rate
* Unemployment Rate
* Consumer Price Index (used to calculate monthly inflation)
* GDP Growth Rate
* NBER Recession Dates (binary target variable)

---

## Data Preparation

The following preprocessing steps were performed:

* Converted recession start and end dates into monthly recession labels
* Constructed a unified monthly timeline
* Merged all economic indicators using observation dates
* Generated lagged yield curve features
* Calculated monthly inflation from CPI
* Resampled quarterly GDP growth to monthly frequency using forward-fill
* Removed incomplete observations required for model estimation

---

## Exploratory Data Analysis

Several macroeconomic indicators were visualized alongside historical recession periods, including:

* Treasury yield spread
* Unemployment rate
* GDP growth

These visualizations provide intuition for the relationships between economic conditions and recession periods before model development.

---

## Feature Engineering

Features used in the model include:

* Yield spread lagged by 3 months
* Yield spread lagged by 4 months
* Yield spread lagged by 5 months
* Yield spread lagged by 6 months
* Federal Funds Rate
* Unemployment Rate
* Monthly Inflation Rate
* GDP Growth Rate

---

## Model

A logistic regression model was developed using scikit-learn.

The response variable is binary:

* 0 = No Recession
* 1 = Recession

The model estimates

[
P(\text{Recession})
===================

\frac{1}{1+e^{-z}}
]

where

[
z=\beta_0+\beta_1X_1+\cdots+\beta_nX_n
]

The notebook also demonstrates how the estimated probabilities are computed manually from the fitted coefficients.

---

## Model Evaluation

The model is evaluated using observations that were not included during training.

Evaluation includes:

* Probability predictions
* Time-series visualization
* Confusion Matrix
* Accuracy
* Precision
* Recall
* F1 Score
* ROC Curve
* Area Under the ROC Curve (AUC)

---

## Repository Structure

```
├── data/
│   ├── recession_dates.xlsx
│   ├── T10Y3M.xlsx
│   ├── DFF.xlsx
│   ├── UNRATE.xlsx
│   ├── CPIAUCSL.xlsx
│   └── GDP_PCH.xlsx
│
├── notebooks/
│   └── recession_prediction.ipynb
│
├── images/
│   ├── yield_curve.png
│   ├── unemployment.png
│   ├── gdp_growth.png
│   └── model_predictions.png
│
├── README.md
└── requirements.txt
```

---

## Technologies Used

* Python
* pandas
* scikit-learn
* Matplotlib
* Jupyter Notebook

---

## Skills Demonstrated

This project demonstrates the following data science skills:

* Data cleaning
* Time-series preprocessing
* Feature engineering
* Exploratory Data Analysis (EDA)
* Logistic regression
* Probability estimation
* Model interpretation
* Classification model evaluation
* Data visualization
* Statistical reasoning

---

## Future Improvements

Potential enhancements include:

* Additional leading economic indicators
* Hyperparameter tuning
* Regularized logistic regression
* Cross-validation
* Time-series cross-validation
* Tree-based machine learning models
* Gradient boosting methods
* Model comparison across multiple algorithms

---

## Author

This project was developed as part of my data science portfolio to demonstrate practical machine learning, statistical modeling, and data analysis skills using publicly available economic data.
