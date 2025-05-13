
# Clustering and Regression Analysis on MathE Student Performance Data

This project investigates student performance using data collected from the MathE platform, analyzing behavioral patterns and predicting correctness using machine learning techniques.

## Project Overview

- Applied K-Means clustering to group students based on performance behaviors.
- Used Linear Regression to model likelihood of correct answers (later deemed unsuitable for binary targets).
- Focused on behavioral features, performance frequency, and educational patterns across multiple countries and topics.

## Dataset

- **Records**: 9,546
- **Features**: Student ID, Country, Question ID, Type of Answer, Question Level, Topic, Subtopic, Keywords
- **Target**: Type of Answer (0 = Incorrect, 1 = Correct)

## Key Steps

### 1. Feature Engineering
- Introduced `Record Count` to quantify repeated student-question interactions.
- Captures performance consistency and learning behavior.

### 2. Data Transformation
- Label encoding of categorical features.
- Scaling commented out (not applied in final model).

### 3. Addressing Imbalances
- Detected overrepresentation in countries, topics, and answer types.
- Used stratified sampling based on combined `Country + Topic + Type of Answer` to ensure fairness in train/test splits.

### 4. Clustering with K-Means
- Selected **k = 4** based on silhouette score (0.58).
- Behavioral clusters:
  - Cluster 0: High performance
  - Cluster 1: Low performance
  - Cluster 2: Average
  - Cluster 3: Outliers

### 5. Regression Analysis
- Applied Linear Regression for binary classification (not ideal).
- Metrics:
  - RMSE: 0.4976
  - R²: 0.0029 (very poor fit)

### 6. Classification Attempt (Mentioned in Report)
- Logistic Regression, Random Forest, and Gradient Boosting tried post-regression.
- All yielded low R² scores and RMSE between 0.58–0.66.

## Key Insights

- K-Means effectively revealed behavioral clusters.
- Regression models failed to predict binary targets accurately.
- Better suited models like Logistic Regression and classification-based evaluation metrics recommended.

## Future Work

- Switch to classification metrics (accuracy, precision, recall, F1).
- Engineer additional behavioral features (e.g., time on task).
- Use sampling methods like SMOTE to handle class imbalance.
- Perform hyperparameter tuning.
- Explore deep learning if data scale permits.

## Technologies Used

- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib, Seaborn


