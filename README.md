# Predicting-football-matches

This repository contains a dataset used to predict the outcomes of football matches. The dataset includes various match statistics, which will be used to train a machine learning model for predicting the result of future football games. This project demonstrates an application of data science and machine learning techniques in the field of sports analytics.

# Dataset Overview

The dataset is stored in a CSV file (Merged_dataset.csv) and includes several key statistics of football matches, with each row representing one match between two teams. The columns in the dataset provide detailed information about both teams' performance during the match, including goals scored, shots taken, fouls, and card details.

# Columns

HomeTeam: Name of the home team in the match.

AwayTeam: Name of the away team in the match.

FTHG: Full-time home goals (number of goals scored by the home team).

FTAG: Full-time away goals (number of goals scored by the away team).

FTR: Full-time result (the result of the match: H = Home win, D = Draw, A = Away win).

HTHG: Half-time home goals (number of goals scored by the home team at half-time).

HTAG: Half-time away goals (number of goals scored by the away team at half-time).

HTR: Half-time result (the result of the match at half-time: H = Home win, D = Draw, A = Away win).

HS: Home shots (total number of shots taken by the home team).

AS: Away shots (total number of shots taken by the away team).

HST: Home shots on target (number of shots on target by the home team).

AST: Away shots on target (number of shots on target by the away team).

HF: Home fouls (number of fouls committed by the home team).

AF: Away fouls (number of fouls committed by the away team).

HC: Home corners (number of corners won by the home team).

AC: Away corners (number of corners won by the away team).

HY: Home yellow cards (number of yellow cards issued to the home team).

AY: Away yellow cards (number of yellow cards issued to the away team).

HR: Home red cards (number of red cards issued to the home team).

AR: Away red cards (number of red cards issued to the away team).

Dataset Overview:
-----------------
Total matches analyzed: 6080

Goal Statistics:
-----------------
Average goals per match:
Home teams: 1.54
Away teams: 1.07

Match Outcomes:
-----------------
Home wins: 2944 (48.4%)
Away wins: 1520 (25.0%)
Draws: 1616 (26.6%)

Card Statistics:
-----------------
Average yellow cards per match: 3.14
Average red cards per match: 0.17

Shot Conversion Rates:
-----------------
Home team conversion rate: inf%
Away team conversion rate: 11.8%
Goal
The main goal of this dataset is to build a predictive model that can predict the outcome of football matches based on the provided statistics. The model will take the match data (e.g., number of goals, shots, fouls, etc.) as input and predict future possible number of goals, shots on target, fouls committed, cards received and the full-time result (i.e., whether the home team wins, the match ends in a draw, or the away team wins).

# Key objectives of this project:
Data Preprocessing: Clean and preprocess the data to handle any missing values, outliers, or inconsistencies.
Feature Engineering: Create additional features or transform existing features to improve the model’s performance.
Exploratory Data Analysis (EDA): Analyze the relationships between various features and the target variable (FTR).
Model Building: Train machine learning models (e.g., Logistic Regression, Random Forest, XGBoost) to predict match outcomes.
Model Evaluation: Evaluate the performance of the models using appropriate metrics (e.g., accuracy, confusion matrix, precision, recall).
Steps to Reproduce the Project
1. Clone the Repository
bash
git clone https://github.com/yourusername/football-match-prediction.git
cd football-match-prediction
2. Install Dependencies
Install the necessary libraries using pip:

bash
pip install -r requirements.txt
3. Load the Dataset
To load and inspect the dataset in Python, use the following code:

python
import pandas as pd

# Load the dataset
df = pd.read_csv("Merged_dataset.csv")

# View the first few rows of the dataset
print(df.head())
4. Preprocess the Data
The data needs to be cleaned before use. Some common preprocessing steps include:

Handling missing values
Encoding categorical variables (e.g., team names)
Feature scaling
5. Build and Train the Model
After preprocessing, you can start building and training the predictive model. Here’s an example using Logistic Regression:

python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LogisticRegression
from sklearn.metrics import accuracy_score

# Select features and target
X = df[['HS', 'AS', 'HST', 'AST', 'HF', 'AF', 'HC', 'AC']]  # Example features
y = df['FTR']  # Full-time result

# Split the data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train the model
model = LogisticRegression()
model.fit(X_train, y_train)

# Make predictions
y_pred = model.predict(X_test)

# Evaluate the model
print("Accuracy:", accuracy_score(y_test, y_pred))
6. Evaluate the Model
Once the model is trained, you can evaluate its performance using various metrics. For example, you can use a confusion matrix to analyze the prediction results.

# Contributing

If you'd like to contribute to this project, feel free to fork the repository and submit a pull request with your changes. Whether it's improving the model, suggesting new features, or fixing bugs, contributions are welcome!


Contact
For questions or inquiries, please contact me at [miraclennakude@gmail.com].
