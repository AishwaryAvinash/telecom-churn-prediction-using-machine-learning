# Telecom Customer Churn Prediction Using MAchine Learning

## Project Description
This project analyses customer-level data from a leading telecom company to predict customer churn. By building predictive models, we identify customers at high risk of leaving and pinpoint key indicators contributing to churn. The insights gained will help telecom companies implement targeted retention strategies, ultimately improving customer loyalty and reducing acquisition costs.

**Note:** Original files related to this project are not shared publicly as they are part of my academic assignments.

## Table of Contents
- [Project Structure](#project-structure)
- [Installation Instructions](#installation-instructions)
- [Libraries Used](#libraries-used)
- [Data Description](#data-description)
- [Model Building](#model-building)
- [Evaluation](#evaluation)
- [Conclusion and Recommendations](#conclusion-and-recommendations)

## Project Structure
- `finallytele.ipynb`: Jupyter notebook containing the code for data analysis, model building, and evaluation.
- `README.md`: This file, which provides an overview of the project, analysis, and instructions for setup and usage.

## Installation Instructions
1. Ensure you have Python 3.10 installed.
2. Open the Jupyter notebook `finallytele.ipynb` and run the cells in sequence.

## Libraries Used
The following libraries were utilized for analysis and model building:
- **pandas**
- **numpy**
- **matplotlib**
- **seaborn**
- **sklearn.decomposition** (PCA, IncrementalPCA)
- **sklearn.preprocessing** (StandardScaler)
- **sklearn.model_selection** (train_test_split)
- **sklearn.linear_model** (LogisticRegression)
- **sklearn.metrics** (metrics, confusion_matrix, classification_report)
- **sklearn.ensemble** (RandomForestClassifier)

## Data Description
The dataset used in this project consists of customer-level data from a telecom company:
1. **application_data.csv**: Contains information about clients at the time of application, focusing on payment difficulties.
2. **previous_application.csv**: Includes details of clients’ previous loan applications, indicating their approval or rejection status.
3. **columns_description.csv**: A data dictionary that describes the variables used.

## Model Building
The model-building process includes the following steps:
1. Data preprocessing, including handling missing values, removing duplicates, and encoding categorical variables.
2. Labeling customers as 1 for those who churn and 0 for those who do not, facilitating easier classification.
3. Retaining only relevant columns.
4. Conducting Exploratory Data Analysis (EDA):
   - **Univariate analysis**: Understanding single variables.
   - **Bivariate analysis**: Exploring relationships between two variables.
   - **Correlation analysis**: Identifying relationships between features.
5. Feature selection to identify the most relevant predictors of churn.
6. Building and training predictive models using Logistic Regression and Random Forest Classifier.
7. Utilizing PCA to retain important information and reduce dimensional complexity.
8. Checking for class imbalance; using the SMOTE oversampling technique, it was discovered that 91.88% were non-churners and 8.12% churners.
9. Deploying Models:
   - Logistic Regression on dataset obtained from applying PCA.
   - Random Forest Classifier on the dataset without PCA and on the dataset obtained after applying PCA.

## Evaluation
All models are evaluated on key metrics for predicting customer churn:
- **Confusion Matrix**
- **Classification Report**:
  - **Logistic Regression**: Precision 0.29, Recall 0.81, F1-score 0.43, Accuracy 0.82.
  - **Random Forest Classifier without PCA**: Precision 0.28, Recall 0.83, F1-score 0.42, Accuracy 0.81.
  - **Random Forest Classifier with PCA**: Precision 0.29, Recall 0.70, F1-score 0.41, Accuracy 0.83.

Recall is crucial as it indicates how many actual churners are correctly predicted. An improvement in recall means the model is better at identifying churners, which is a primary requirement stated in problem statement.

## Conclusion and Recommendations
This project highlights the importance of predicting customer churn in the telecom industry and provides actionable insights for improving customer retention strategies:
- Focus on customers who show a decline in service usage starting from the action month.
- Identify that customers with a tenure of 2 to 5 years exhibit higher churn rates.
- Average revenue per user is a significant predictor of churn.
- Observe a significant drop in data usage among churners in the 3rd month, nearly reaching zero in the 4th month.
- Compare 2G and 3G service users; churners predominantly use 2G, indicating inadequate data services.
- Analyze total recharge amounts in the first month, as churners often recharge more initially but decrease significantly in subsequent months.

**Note:** Due to computational constraints, further hyperparameter tuning options were not explored.
