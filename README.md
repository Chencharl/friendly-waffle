# friendly-waffle
stroke-risk-prediction

# Stroke Risk Prediction using Machine Learning

This project aims to develop a machine learning-based stroke risk prediction model using a publicly available Kaggle dataset. Our analysis evaluates multiple classification algorithms under both imbalanced and resampled conditions to identify key predictors of stroke, such as age, BMI, hypertension, and heart disease.

## 📁 Project Structure
├── final_report.Rmd # Main reproducible report in R Markdown
├── final_report.pdf # Rendered PDF report
├── data/
│ └── stroke_data.csv # Dataset from Kaggle (https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
├── figures/
│ ├── eda_plot1.png # EDA visualizations
│ └── model_results.png # Model performance comparison
├── README.md # This file


## Dataset

- Source: [Kaggle Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset)
- Observations: 5,110
- Features: 10 (e.g., age, BMI, hypertension, heart disease, smoking status)
- Response variable: `stroke` (binary: 1 = stroke occurred, 0 = no stroke)

## Methods

We used the following models:
- Logistic Regression
- Decision Tree
- Random Forest
- XGBoost (Gradient Boosting)

To address class imbalance (only ~5% of stroke cases), we applied **SMOTE** (Synthetic Minority Oversampling Technique) during model training and evaluation.

## Evaluation Metrics

Models were evaluated using:
- AUC (Area Under the Curve)
- Accuracy
- F1-score

Final model selection was based on performance aggregated across these metrics.

## Key Findings

- **Random Forest with SMOTE** outperformed other models.
- **Age** was the most influential predictor.
- **BMI**, **average glucose**, **hypertension**, and **heart disease** were also important.
- **Marital status** appeared predictive but likely acted as a confounder due to age.

## Authors

Yanzhi Hua – EDA, logistic regression, XGBoost implementation
Chen Yang – SMOTE balancing, random forest modeling, results synthesis


## Reproducibility

To reproduce the results:
1. Clone this repository
2. Open `final_report.Rmd` in RStudio
3. Run all chunks (requires R packages listed below)

## Required R Packages

```r
install.packages(c("tidyverse", "caret", "xgboost", "DMwR", "pROC", "randomForest", "knitr"))
