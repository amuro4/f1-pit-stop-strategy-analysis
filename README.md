# A Methods Atlas of Formula 1 Pit Stop Strategy and Lap Performance

## Project Overview

This repository contains my MATH 4230 capstone project for Applied Statistical Methods for Data Science.

The project uses Formula 1 lap-level data to compare several statistical learning methods for two main tasks:

1. Predicting lap time using regression methods.
2. Predicting whether a driver will pit on the next lap using classification methods.

The final report is written in LaTeX and includes exploratory data analysis, simple linear regression, multiple linear regression, logistic regression, cross-validation, bootstrap, ridge regression, lasso regression, decision trees, tree ensembles, support vector machines, K-nearest neighbors, PCA, a neural network, and a final method comparison.

## Dataset Source

Dataset: **F1 Strategy Dataset | Pit Stop Prediction**  
Source: Kaggle  
Author: Aadi Gupta  
Link: https://www.kaggle.com/datasets/aadigupta1601/f1-strategy-dataset-pit-stop-prediction/data  
Date accessed: May 17, 2026

The raw dataset is not included in this repository because large data files can cause GitHub upload issues. To reproduce the project, download the dataset from Kaggle and place the raw files in the correct local data folder before running the scripts.

## Main Research Questions

The project focuses on two main modeling questions:

1. Can lap-level predictors explain or predict `lap_time_s`?
2. Can lap-level predictors predict `pit_next_lap`?

The regression target is:

```text
lap_time_s
```

The classification target is:

```text
pit_next_lap
```

## Main Results

The best regression method was **lasso regression**. It had the lowest test RMSE for predicting lap time.

The best classification method was **boosting**. It had the strongest AUC for predicting whether a driver would pit on the next lap.

The project also shows that interpretability matters. Logistic regression and decision trees were easier to explain, even when they were not always the strongest models by raw predictive performance.

## Repository Structure

```text
.
├── README.md
├── main_condensed.tex
├── references_updated.bib
├── figures/
│   ├── chapter figures used in the final report
│   └── exploratory data analysis figures
├── report/
│   └── A_Methods_Atlas_of_Formula_1_Pit_Stop_Strategy_and_Lap_Performance FINAL.pdf
├── results4github/
│   └── tables/
│       ├── summary_statistics.csv
│       ├── method_comparison.csv
│       ├── method_recommendations.csv
│       └── selected chapter result tables
└── scripts/
    ├── 00_setup.R
    ├── 01_clean_build_modeling_data.R
    ├── 02_split_data.R
    ├── 03_dataset_profile_eda.R
    ├── 04_slr_lap_time.R
    ├── 05_mlr_lap_time.R
    ├── 06_logistic_pit_next_lap.R
    ├── 07_resampling_cv_bootstrap.R
    ├── 08_regularization_ridge_lasso.R
    ├── 09_decision_trees.R
    ├── 10_tree_ensembles.R
    ├── 11_svm.R
    ├── 12_knn.R
    ├── 13_pca.R
    ├── 14_neural_network.R
    └── 15_method_comparison.R
```

## How to Reproduce the Project

1. Clone this repository.

```bash
git clone https://github.com/amuro4/amuro4-A-Methods-Atlas-of-Formula-1-Pit-Stop-Strategy-and-Lap-Performance.git
cd amuro4-A-Methods-Atlas-of-Formula-1-Pit-Stop-Strategy-and-Lap-Performance
```

2. Download the dataset from Kaggle.

Dataset link:

```text
https://www.kaggle.com/datasets/aadigupta1601/f1-strategy-dataset-pit-stop-prediction/data
```

3. Place the raw dataset files in the local project data folder.

```text
data/raw/
```

4. Open the project in RStudio.

5. Run the scripts in order.

```r
source("scripts/00_setup.R")
source("scripts/01_clean_build_modeling_data.R")
source("scripts/02_split_data.R")
source("scripts/03_dataset_profile_eda.R")
source("scripts/04_slr_lap_time.R")
source("scripts/05_mlr_lap_time.R")
source("scripts/06_logistic_pit_next_lap.R")
source("scripts/07_resampling_cv_bootstrap.R")
source("scripts/08_regularization_ridge_lasso.R")
source("scripts/09_decision_trees.R")
source("scripts/10_tree_ensembles.R")
source("scripts/11_svm.R")
source("scripts/12_knn.R")
source("scripts/13_pca.R")
source("scripts/14_neural_network.R")
source("scripts/15_method_comparison.R")
```

6. Compile the LaTeX report.

Main LaTeX file:

```text
main_condensed.tex
```

Bibliography file:

```text
references_updated.bib
```

The compiled final PDF is available in the `report/` folder.

## Output Files

Figures are saved in:

```text
figures/
```

Selected result tables for GitHub are saved in:

```text
results4github/tables/
```

The full local project may also create additional folders such as:

```text
results/tables/
results/models/
data/processed/
```

Some large outputs are intentionally excluded from GitHub to keep the repository small enough to upload.

## Notes on Large Files

GitHub has file size limits, so this repository does not include every large file generated during the project.

Files that may be excluded include:

```text
data/raw/
data/processed/
results/models/
large prediction CSV files
.RData files
.Rhistory files
```

The project can still be reproduced by downloading the dataset from Kaggle and running the scripts in order.

## R Packages Used

Main R packages used in this project include:

```text
tidyverse
janitor
lubridate
skimr
broom
ggplot2
corrplot
car
leaps
glmnet
tree
rpart
rpart.plot
randomForest
gbm
e1071
class
nnet
pROC
```

The setup script loads the required packages and installs missing packages when needed.

## Final Recommendation

For lap-time regression, I recommend **lasso regression** because it had the best test RMSE while still being reasonably interpretable.

For pit-next-lap classification, I recommend **boosting** because it had the strongest AUC.

For explanation-focused work, I would also keep **logistic regression** and **decision trees** because they are easier to interpret and explain.

## Limitations

The dataset does not include several important race-status and circuit-condition variables, including Safety Car, Virtual Safety Car, yellow flags, red flags, track temperature, air temperature, circuit length, tire availability, and pit lane time loss.

Because of this, the project should be viewed as a comparison of statistical learning methods rather than a complete Formula 1 strategy system.

## Author

Adrian Muro  
MATH 4230 Applied Statistical Methods for Data Science  
California State University, Bakersfield
