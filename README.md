NYC Airbnb Price Prediction Model
Project Overview
This project aims to predict Airbnb listing prices in New York City using machine learning models. Utilizing the 2023 NYC Airbnb open dataset, we analyze key factors influencing rental prices and build a predictive model.

Dataset
File Name: NYC-Airbnb-2023.csv

Feature Description:

neighbourhood_group: Borough (Manhattan, Brooklyn, etc.)

room_type: Room type (Entire home/apt, Private room, etc.)

price: Price (USD)

Latitude & Longitude coordinates

Review metrics (number of reviews, reviews per month, etc.)

Tech Stack
Python 3.8+

Main Libraries: Pandas, Scikit-learn, Matplotlib, Seaborn

Machine Learning Algorithm: Optimized Random Forest Regression

Analysis Workflow
Data Exploration:

Price distribution

Geographical distribution

Room type analysis

Feature Engineering:

Handling outliers (removing extreme values <
20
o
r
>
20or>1000)

Categorical variable encoding (One-Hot Encoding)

Numerical feature standardization

Model Building:

Data processing pipeline construction

Hyperparameter optimization using Grid Search

Model Evaluation:

R² Score: 0.62

RMSE: $78.23

Key Findings
Price Distribution: Most listings are priced between 
50
−
50−300

Geographical Impact: Highest density of listings in Manhattan and Brooklyn

Important Features:

Room type (Entire homes command highest prices)

Geographic location (Latitude shows significant impact)

Availability (Number of available days)

Usage Instructions
Install dependencies:

bash
pip install -r requirements.txt  
Run Jupyter Notebook:

bash
jupyter notebook NYC_Rent_Forecasting.ipynb  
Parameter tuning: Modify the parameter grid in GridSearchCV

Future Improvements
Incorporate external data (subway station locations, tourist attractions)

Experiment with deep learning models

Build a price anomaly detection system
