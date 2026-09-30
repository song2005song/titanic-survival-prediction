# titanic-survival-prediction
Titanic survival prediction using Python and scikit-learn

Titanic Survival Prediction

A machine learning project that predicts passenger survival using the Kaggle Titanic dataset.

This project focuses on the complete machine learning workflow, including exploratory data analysis, data preprocessing, feature engineering, model comparison, and hyperparameter tuning.

Project Overview

The goal of this project is to predict whether a passenger survived the Titanic disaster based on passenger information such as age, sex, passenger class, family relationships, ticket information, and fare.

The project follows a typical supervised machine learning workflow:

Exploratory Data Analysis
Data Preprocessing
Baseline Model Comparison
Feature Engineering
Model Evaluation
Hyperparameter Tuning
Final Prediction
Kaggle Submission
Dataset

This project uses the Titanic - Machine Learning from Disaster dataset from Kaggle.

The dataset contains passenger information including:

Passenger class
Sex
Age
Number of siblings/spouses aboard
Number of parents/children aboard
Ticket
Fare
Cabin
Port of embarkation

The target variable is:

Survived = 1: Survived
Survived = 0: Did not survive

The Kaggle competition evaluates predictions using classification accuracy.

Technologies
Python
Pandas
NumPy
Matplotlib
Scikit-learn
Jupyter Notebook
Exploratory Data Analysis

The initial analysis included:

Dataset inspection
Numerical feature distributions
Correlation analysis
Examination of missing values
Exploration of passenger characteristics
Data Preprocessing

A Scikit-learn preprocessing pipeline was used to handle numerical and categorical features.

Numerical Features

The numerical preprocessing pipeline includes:

Median imputation
Square-root transformation
Standardization
Categorical Features

The categorical preprocessing pipeline includes:

Most-frequent-value imputation
One-hot encoding
Handling previously unseen categories

ColumnTransformer was used to apply different preprocessing pipelines to numerical and categorical variables.

Feature Engineering

Several additional features were created to capture relationships that are not directly represented by the original variables.

FamilySize
FamilySize = SibSp + Parch + 1
IsAlone

Indicates whether a passenger was traveling alone.

Title

Extracted from the passenger's name.

Deck

Extracted from the first character of the cabin information.

TicketGroupSize

Represents the number of passengers sharing the same ticket.

FarePerPerson

Calculates the fare relative to the size of the ticket group.

These features were incorporated into the preprocessing pipeline and evaluated through the modeling process.

Models

Several classification algorithms were compared:

SGD Classifier
Logistic Regression
Random Forest
K-Nearest Neighbors

Cross-validation was used to evaluate model performance.

Hyperparameter Tuning

GridSearchCV was used to search for suitable hyperparameters.

The main models and parameters explored included:

Logistic Regression
C
SGD Classifier
loss
alpha
Random Forest
n_estimators
max_depth
min_samples_split
max_features
Final Model

After comparing the candidate models and performing hyperparameter tuning, Logistic Regression was selected for the final prediction.

The final model was trained using the processed training data and used to generate predictions for the Kaggle test dataset.

Results
Evaluation	Result
Cross-validation accuracy	~83%
Kaggle score	0.77990

The Kaggle submission achieved an accuracy of 0.77990 on the competition leaderboard.

Repository Contents
titanic-survival-prediction/
│
├── README.md
├── titanic-survival-prediction.ipynb
└── .gitignore

The Jupyter Notebook contains the complete analysis, preprocessing, feature engineering, model comparison, hyperparameter tuning, and prediction workflow.

What I Learned

Through this project, I practiced:

Exploratory data analysis
Handling missing data
Numerical and categorical preprocessing
Scikit-learn pipelines
ColumnTransformer
Feature engineering
One-hot encoding
Cross-validation
Model comparison
Hyperparameter tuning with GridSearchCV
Classification with Logistic Regression, SGD, Random Forest, and KNN
Preparing predictions for a Kaggle competition
Kaggle

This project was developed as part of the Titanic - Machine Learning from Disaster competition on Kaggle.

Kaggle Titanic Competition
