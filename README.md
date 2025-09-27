IPL Score Prediction Project

Predicting cricket match scores in the Indian Premier League (IPL) using historical ball-by-ball data and machine learning models. This project demonstrates data cleaning, feature engineering, and predictive modeling for cricket analytics.

Project Overview

The main goal of this project is to predict the total score of a cricket team in an IPL match based on the match situation at any given point during the innings. The model uses historical ball-by-ball data and considers factors like current runs, wickets, overs, and performance in the last 5 overs.

Dataset

The dataset contains ball-by-ball information of IPL matches, including:

mid : Match ID

date : Date of the match

venue : Stadium/ground

bat_team : Batting team

bowl_team : Bowling team

batsman : Name of the batsman

bowler : Name of the bowler

runs : Runs scored on that ball

wickets : Wickets fallen on that ball

overs : Current over number

runs_last_5 : Runs scored in the last 5 overs

wickets_last_5 : Wickets fallen in the last 5 overs

striker : Balls faced by striker

non-striker : Balls faced by non-striker

total : Total score of the innings

Data Cleaning

The dataset underwent the following preprocessing steps:

Removed unnecessary columns: mid, venue, batsman, bowler, striker, non-striker.

Kept only consistent teams from IPL seasons to maintain uniformity.

Removed the first 5 overs of each innings to focus on the mid and death overs where scoring is crucial.

Converted date column from string to datetime format.

Exploratory Data Analysis

Correlation analysis between features (runs, wickets, overs, runs_last_5, wickets_last_5) and the total score.

Visualization of relationships between features using heatmaps and other plots.

Data Preprocessing

Converted categorical features (bat_team and bowl_team) into numerical format using One-Hot Encoding.

Split the dataset into training and testing sets based on the year:

Training: IPL Seasons 1 to 9 (2008–2016)

Testing: IPL Season 10 (2017)

Model Building

The project experimented with multiple regression models to predict final scores:

Linear Regression

MAE: 12.11

RMSE: 15.84

Decision Tree Regression

MAE: 17.08

RMSE: 23.04

Random Forest Regression

MAE: 13.76

RMSE: 18.17

AdaBoost Regression (with Linear Regression as base)

MAE: 12.21

RMSE: 15.79

Conclusion: Linear Regression and AdaBoost models provided the most accurate predictions.

Score Prediction Function

A function predict_score is implemented to predict the final score of a team given:

Batting team

Bowling team

Current overs, runs, wickets

Runs scored and wickets fallen in the last 5 overs
final_score = predict_score(
    batting_team='Kolkata Knight Riders',
    bowling_team='Delhi Daredevils',
    overs=9.2,
    runs=79,
    wickets=2,
    runs_in_prev_5=60,
    wickets_in_prev_5=1
)
print("The final predicted score (range): {} to {}".format(final_score-10, final_score+5))
Technologies & Libraries Used

Programming Language: Python

Data Analysis & Manipulation: Pandas, NumPy

Data Visualization: Matplotlib, Seaborn

Machine Learning: Scikit-learn (Linear Regression, Decision Tree, Random Forest, AdaBoost)

Future Work

Incorporate additional features like player performance, pitch conditions, and weather.

Use advanced models like XGBoost or deep learning techniques for better accuracy.

Build a real-time prediction dashboard using Streamlit or Flask.

ipl-score-prediction/
│
├── ipl.csv                # Dataset
├── IPL_Score_Prediction.ipynb  # Jupyter Notebook with full analysis
├── requirements.txt       # Required Python libraries
└── README.md              # Project documentation
