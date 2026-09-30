# Titanic Survival Prediction

A machine learning project that predicts passenger survival using the Kaggle Titanic dataset.

This project covers a complete machine learning workflow, including exploratory data analysis, data preprocessing, feature engineering, model comparison, and hyperparameter tuning.

## Project Overview

The goal of this project is to predict whether a passenger survived the Titanic disaster based on passenger information such as age, sex, passenger class, family relationships, ticket information, and fare.

The project follows the following machine learning workflow:

1. Exploratory Data Analysis
2. Data Preprocessing
3. Baseline Model Comparison
4. Feature Engineering
5. Feature-Engineered Preprocessing
6. Model Evaluation
7. Hyperparameter Tuning
8. Final Prediction
9. Kaggle Submission

## Dataset

This project uses the [Titanic - Machine Learning from Disaster](https://www.kaggle.com/competitions/titanic) dataset from Kaggle.

The dataset contains passenger information including:

- Passenger class
- Sex
- Age
- Number of siblings/spouses aboard
- Number of parents/children aboard
- Ticket
- Fare
- Cabin
- Port of embarkation

The target variable is:

- `Survived = 1`: Survived
- `Survived = 0`: Did not survive

The Kaggle competition evaluates predictions using classification accuracy.

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Exploratory Data Analysis

The initial analysis included:

- Dataset inspection
- Numerical feature distributions
- Correlation analysis
- Examination of missing values
- Exploration of passenger characteristics

## Data Preprocessing

Scikit-learn pipelines were used to process numerical and categorical features separately.

### Numerical Features

The numerical preprocessing pipeline includes:

- Median imputation
- Square-root transformation
- Standardization

### Categorical Features

The categorical preprocessing pipeline includes:

- Most-frequent-value imputation
- One-hot encoding
- Handling previously unseen categories

`ColumnTransformer` was used to apply different preprocessing pipelines to numerical and categorical features.

## Feature Engineering

Several features were created to capture additional information from the original dataset.

### FamilySize

The total number of family members traveling with the passenger:

```text
FamilySize = SibSp + Parch + 1
```

### IsAlone

A binary feature indicating whether a passenger was traveling alone.

### Title

The passenger's title was extracted from the `Name` column.

### Deck

The first character of the `Cabin` value was extracted to represent the passenger's deck.

### TicketGroupSize

The number of passengers sharing the same ticket was calculated using ticket frequency.

### FarePerPerson

The fare was divided by the ticket group size:

```text
FarePerPerson = Fare / TicketGroupSize
```

These engineered features were incorporated into the preprocessing and modeling workflow.

## Baseline Models

Several classification models were initially compared:

- SGD Classifier
- Logistic Regression
- Random Forest
- K-Nearest Neighbors

Cross-validation was used to evaluate the models.

## Hyperparameter Tuning

`GridSearchCV` was used to search for suitable hyperparameters for the candidate models.

### Logistic Regression

The following hyperparameter was explored:

- `C`

### SGD Classifier

The following hyperparameters were explored:

- `loss`
- `alpha`

### Random Forest

The following hyperparameters were explored:

- `n_estimators`
- `max_depth`
- `min_samples_split`
- `max_features`

## Final Model

After model comparison and hyperparameter tuning, Logistic Regression was selected as the final model.

The final model was trained using the processed training data and used to generate predictions for the Kaggle test dataset.

## Results

| Evaluation | Result |
|---|---|
| Cross-validation accuracy | ~83% |
| Kaggle score | 0.77990 |

The final Kaggle submission achieved an accuracy of **0.77990**.

## Repository Contents

```text
titanic-survival-prediction/
│
├── README.md
├── titanic-survival-prediction.ipynb
└── .gitignore
```

The Jupyter Notebook contains the complete analysis and modeling workflow, including exploratory data analysis, preprocessing, feature engineering, model comparison, hyperparameter tuning, and final prediction.

## What I Learned

Through this project, I practiced:

- Exploratory data analysis
- Handling missing data
- Numerical and categorical preprocessing
- Scikit-learn pipelines
- `ColumnTransformer`
- Feature engineering
- One-hot encoding
- Cross-validation
- Model comparison
- Hyperparameter tuning with `GridSearchCV`
- Logistic Regression
- SGD Classification
- Random Forest
- K-Nearest Neighbors
- Preparing predictions for a Kaggle competition

## Kaggle

This project was developed as part of the Kaggle Titanic competition.

[View the Kaggle Competition](https://www.kaggle.com/competitions/titanic)
