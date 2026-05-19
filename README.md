# A Methods Atlas of Formula 1 Pit Stop Strategy and Lap Performance

## Project Overview

This repository contains my MATH 4230 capstone project. The project uses Formula 1 lap-level data to compare several statistical learning methods for two main tasks:

1. Predicting lap time using regression methods.
2. Predicting whether a driver will pit on the next lap using classification methods.

The final report is written in LaTeX and includes exploratory data analysis, model fitting, cross-validation, bootstrap, regularization, tree methods, SVM, KNN, PCA, a neural network, and a final method comparison.

## Dataset Source

Dataset: **F1 Strategy Dataset | Pit Stop Prediction**  
Source: Kaggle  
Author: Aadi Gupta  
Link: https://www.kaggle.com/datasets/aadigupta1601/f1-strategy-dataset-pit-stop-prediction/data  
Date accessed: May 17, 2026

The raw dataset is not included in this repository if it is too large for GitHub. To reproduce the project, download the dataset from Kaggle and place the files in the correct `data/raw/` folder before running the scripts.

## Main Questions

The project focuses on these two main modeling questions:

- Regression question: Can lap-level predictors explain or predict `lap_time_s`?
- Classification question: Can lap-level predictors predict `pit_next_lap`?

## Main Results

The best regression method was **lasso regression**, with the lowest test RMSE for predicting lap time.

The best classification method was **boosting**, with the strongest AUC for predicting whether a driver would pit on the next lap.

The project also shows that interpretability matters. Logistic regression and decision trees were easier to explain, even when they were not the strongest models by raw performance.

## Repository Structure

```text
.
├── README.md
├── main_condensed.tex
├── references_updated.bib
├── figures/
│   ├── ch03_fig01_slr_fitted_line.png
│   ├── ch04_fig01_residuals_vs_fitted.png
│   ├── ch05_fig02_roc_curve.png
│   ├── ch06_fig03_bootstrap_tyre_life_slope.png
│   ├── ch07_fig01_lambda_cv_plot.png
│   ├── ch08_fig01_regression_tree.png
│   ├── ch09_fig01_random_forest_importance.png
│   ├── ch10_fig01_svm_metrics.png
│   ├── ch11_fig01_knn_cv_error_curve.png
│   ├── ch12_fig01_pca_scree_plot.png
│   └── ch13_fig01_neural_network_metrics.png
├── results/
│   └── tables/
│       ├── summary_statistics.csv
│       ├── method_comparison.csv
│       ├── method_recommendations.csv
│       └── chapter-level result tables
├── scripts/
│   ├── 00_setup.R
│   ├── 01_clean_build_modeling_data.R
│   ├── 02_split_data.R
│   ├── 03_dataset_profile_eda.R
│   ├── 04_slr_lap_time.R
│   ├── 05_mlr_lap_time.R
│   ├── 06_logistic_pit_next_lap.R
│   ├── 07_resampling_cv_bootstrap.R
│   ├── 08_regularization_ridge_lasso.R
│   ├── 09_decision_trees.R
│   ├── 10_tree_ensembles.R
│   ├── 11_svm.R
│   ├── 12_knn.R
│   ├── 13_pca.R
│   ├── 14_neural_network.R
│   └── 15_method_comparison.R
└── final_report.pdf
