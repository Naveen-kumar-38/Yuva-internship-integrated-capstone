# Customer Subscription Prediction and Customer Segmentation Using Data Science

## YUVA Internship – Week 6 Integrative Capstone

This project is the final integrative capstone developed as part of the YUVA Virtual Data Science with Python Internship.

The project demonstrates a complete data science workflow using the UCI Bank Marketing dataset. It combines data acquisition, data cleaning, exploratory data analysis, feature engineering, unsupervised learning, supervised learning, model evaluation, and business-oriented interpretation.

## Project Objective

The main objectives of this project are:

- Analyze customer and campaign data.
- Identify important patterns through exploratory data analysis.
- Segment customers using K-Means clustering.
- Predict bank term-deposit subscription using supervised learning.
- Compare Logistic Regression and Random Forest.
- Evaluate models using multiple classification metrics.
- Validate model performance using Stratified 5-Fold Cross-Validation.
- Generate practical recommendations from the results.

## Dataset

The project uses the UCI Bank Marketing dataset.

The dataset contains information about customers contacted during bank marketing campaigns.

### Dataset characteristics

- 45,211 customer records
- 17 original columns
- Demographic information
- Financial information
- Communication details
- Campaign-related information
- Binary target variable `y`

The target variable indicates whether a customer subscribed to a bank term deposit.

## Data Science Pipeline

The project follows the complete pipeline:

1. Data acquisition
2. Data quality assessment
3. Data cleaning
4. Feature engineering
5. Exploratory Data Analysis
6. Customer segmentation
7. Predictive modeling
8. Cross-validation
9. Model evaluation
10. Feature importance analysis
11. Integrated analysis
12. Recommendations

## Feature Engineering

The project creates additional features including:

- `age_group`
- `balance_category`
- `previous_contact`

The `duration` feature is excluded from predictive modeling because it can introduce data leakage when predicting customer subscription before or at the beginning of an interaction.

## Exploratory Data Analysis

The project analyzes:

- Customer age distribution
- Account balance distribution
- Subscription distribution
- Subscription rate by job
- Subscription rate by education
- Balance by subscription outcome
- Correlations among numerical variables

## Customer Segmentation

K-Means clustering is used to identify customer segments.

The clustering features include:

- Age
- Balance
- Campaign
- Days since previous contact
- Number of previous contacts

The Elbow Method and Silhouette Score are used to select the number of clusters.

### Clustering Result

The final analysis selected:

- Number of clusters: **2**
- Silhouette Score: **0.4622**

The two clusters show different campaign histories and subscription behavior.

## Supervised Learning

Two classification models are implemented:

### Logistic Regression

Used as a baseline classification model.

### Random Forest

Used as the main nonlinear ensemble classification model.

The models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC

## Model Results

### Test Set Performance

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 76.71% | 28.20% | 64.08% | 39.17% | 0.778 |
| Random Forest | 82.03% | 34.91% | 62.00% | 44.67% | 0.798 |

Random Forest achieved the strongest overall performance.

## Cross-Validation

Stratified 5-Fold Cross-Validation was performed.

| Model | Accuracy | Precision | Recall | F1 Score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Logistic Regression | 76.28% | 27.52% | 62.85% | 38.28% | 0.771 |
| Random Forest | 81.60% | 33.91% | 60.33% | 43.41% | 0.792 |

The Random Forest model remained stronger during cross-validation.

## Customer Segment Findings

The final segmentation produced two customer groups.

| Cluster | Customers | Average Age | Average Balance | Subscription Rate |
|---|---:|---:|---:|---:|
| Cluster 0 | 38,226 | 40.96 | 1,330.73 | 9.98% |
| Cluster 1 | 6,985 | 40.83 | 1,534.87 | 21.10% |

Cluster 1 has a considerably higher subscription rate and a much stronger history of previous customer contact.

## Important Features

Random Forest feature importance identified several influential variables, including:

- Previous campaign outcome
- Contact type
- Age
- Days since previous contact
- Account balance
- Campaign day
- Housing status
- Previous-contact information

## Key Insights

- Random Forest performed better than Logistic Regression.
- The Random Forest model achieved a test ROC-AUC of 0.798.
- Two meaningful customer segments were identified.
- Cluster 1 had a 21.10% subscription rate compared with 9.98% for Cluster 0.
- Previous customer engagement was an important differentiating factor between the segments.
- Class imbalance makes precision, recall, F1-score, and ROC-AUC important alongside accuracy.

## Recommendations

Based on the analysis:

1. Prioritize customers with stronger historical campaign engagement.
2. Develop different marketing strategies for different customer segments.
3. Use predictive probabilities to prioritize potential customers.
4. Monitor precision and recall rather than relying only on accuracy.
5. Periodically retrain the model as customer behavior changes.
6. Combine machine learning predictions with business expertise.

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

## Repository Structure

```text
yuva-internship-integrative-capstone
│
├── screenshots
├── output
├── Task_6_Integrative_Capstone.ipynb
└── README.md