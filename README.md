# Concrete Strength Prediction Application

A comprehensive Data Science project for predicting concrete compressive strength based on material composition and curing age using the UCI Concrete Compressive Strength dataset.

## Overview

This project implements:
- **Data Preprocessing:** Data cleaning, scaling, train-test split
- **EDA:** Analysis of strength by age, feature distributions, and correlations
- **Feature Engineering:** Water-cement ratio, cement-age interaction, log transformation of age
- **Modeling:** Predict-Mean baseline, OLS Linear Regression, Ridge, Lasso, SVR
- **Ablation Study:** Raw features vs engineered features, Ridge vs Lasso comparison
- **Evaluation:** 5-Fold Cross Validation with MAE, RMSE, and R²
- **Error Analysis:** Residual plots and error slicing by age bins and strength ranges
- **Application:** Predictive system for estimating concrete compressive strength
- **Explainability:** Feature impact discussion and practical interpretation of results

Dataset
Dataset Name: Concrete Compressive Strength
Dataset ID: UCI-165
Source: UCI Machine Learning Repository
Description: The dataset contains concrete ingredients such as cement, slag, fly ash, water, superplasticizer, coarse aggregate, fine aggregate, and age, used to predict concrete compressive strength.
Input Features
Cement
Blast Furnace Slag
Fly Ash
Water
Superplasticizer
Coarse Aggregate
Fine Aggregate
Age
Target
Concrete compressive strength

Usage
1. Run EDA
jupyter notebook EDA_concrete.ipynb
2. Run Feature Engineering
jupyter notebook Feature.ipynb
3. Run Model Training
jupyter notebook Train_model.ipynb
Research Questions

RQ1: Are linear models sufficient to describe the relationship between material composition and compressive strength?

This project evaluates OLS, Ridge, and Lasso to determine whether linear relationships are enough for strength prediction.

RQ2: Does feature engineering improve the performance of linear regression models?

The study compares raw features with engineered features such as water-cement ratio and cement-age interaction.

RQ3: Can SVR reduce prediction errors, especially at extreme strength levels?

SVR with RBF kernel is used as a non-linear alternative and compared against linear models.

Feature Engineering

The following engineered features are included:

Water_Cement_Ratio = Water / Cement
Cement_Age_Interaction = Cement × Age
Log_Age = log(Age + 1)

These features are designed to better capture material behavior and curing effects.

Model Results
Models Evaluated
Predict-Mean Baseline
OLS Linear Regression
Ridge Regression
Lasso Regression
SVR (RBF Kernel)
Evaluation Protocol
Train-test split
5-Fold Cross Validation
Metrics:
MAE
RMSE
R²
General Findings
Linear models provide a reasonable baseline
Ridge and Lasso help stabilize learning when features are correlated
SVR generally performs best because the relationship between material composition and compressive strength is non-linear
Engineered features improve interpretability and may improve linear model performance
Data Visualization

The project includes:

Scatter plot of age vs compressive strength
Boxplot by age bins
Correlation heatmap
Distribution plots for all input variables
Residual plots
Actual vs predicted plots

These visualizations help understand both data patterns and model behavior.

Error Analysis
Error Slicing

Errors are analyzed across:

Age bins
Strength ranges
Residual Analysis

Residual plots are used to:

detect bias
inspect heteroscedasticity
observe whether errors increase in extreme ranges
Main Contributions
1. Machine Learning Pipeline

A full regression pipeline is implemented:

preprocessing
feature engineering
model training
cross-validation
error slicing
residual analysis
2. Ablation Study

The project compares:

raw features vs engineered features
Ridge vs Lasso
linear models vs SVR
3. Practical Prediction Support

The system supports estimating compressive strength from input material composition and age, which can assist concrete mix decision-making.

Applications

This project can be extended into an application where users:

enter material composition values
receive predicted compressive strength
view feature-based explanation
receive warning if the input is outside the normal data range
Limitations and Risks
Data Limitations
The dataset is relatively small compared to industrial-scale data
The data may not cover all real-world material conditions
Measurement conditions and lab setup may vary from practical deployment environments
Modeling Limitations
Linear models may underfit complex relationships
SVR is more accurate but less interpretable
Extreme strength values may still have higher prediction errors
Deployment Risks
Predictions should not replace engineering judgment
Out-of-distribution inputs may reduce reliability
Real construction settings may differ from controlled dataset conditions
Conclusion

This project shows that concrete compressive strength can be predicted using machine learning methods from material composition and curing age. Linear regression models provide interpretable baselines, while SVR offers stronger predictive performance for non-linear relationships. Feature engineering and error analysis improve both understanding and reliability of the modeling pipeline.

Future Work
Add an interactive prediction app
Add chatbot support for project explanation
Test additional models such as Random Forest or XGBoost
Explore neural networks as an optional comparison
Improve explainability with SHAP or coefficient-based dashboards
