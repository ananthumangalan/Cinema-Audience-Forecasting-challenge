# Cinema-Audience-Forecasting-challenge
Predict daily theatre audience counts across multiple locations.

# Cinema Audience Forecasting Challenge

## Project Overview

This project focuses on a time-series forecasting problem related to cinema audience attendance. The goal is to predict future audience counts for different theatres using booking and theatre-related data collected from two separate platforms: **BookNow** and **CinePOS**.

Audience demand in cinemas can vary based on several factors such as holidays, weekends, theatre type, booking behavior, and historical attendance trends. This project aims to analyze these patterns and build a machine learning model that can forecast audience counts accurately.

## Objective

The main objective of this project is to predict the `audience_count` for each theatre and show date.

The final prediction is required in the following format:

- `ID = book_theater_id + show_date`
- `audience_count = predicted number of audience visits`

## Dataset Description

The dataset is provided as part of a Kaggle competition and contains information from two booking platforms:

- **BookNow**: An online booking and aggregation platform where users can search theatres and book tickets in advance.
- **CinePOS**: A point-of-sale system installed at theatres that tracks on-site ticket sales.

The dataset contains theatre details, booking records, daily audience visits, date information, and theatre mapping between the two platforms.

## Files Used

The dataset contains the following CSV files:

- `cinePOS_theaters.csv` - CinePOS theatre information
- `booknow_theaters.csv` - BookNow theatre information
- `movie_theater_id_relation.csv` - Mapping between BookNow and CinePOS theatres
- `cinePOS_booking.csv` - CinePOS booking data
- `booknow_booking.csv` - BookNow booking data
- `booknow_visits.csv` - Daily audience count data
- `date_info.csv` - Calendar/date-related information
- `sample_submission.csv` - Submission format containing `ID` and `audience_count`

## Important Notes

- Audience counts can be influenced by holidays, weekends, theatre type, and booking trends.
- The dataset is anonymized.
- Latitude and longitude values are approximate.
- Both POS booking patterns and online booking patterns are useful for forecasting future theatre audiences.
- Some theatres may be closed on certain days, leading to zero audience counts.
- Closed theatre days may be present in the dataset but ignored during final scoring.

## Tech Stack

- Python
- Pandas
- NumPy
- Matplotlib / Seaborn
- Scikit-learn
- Machine Learning
- Time-Series Forecasting
- Kaggle Notebook

## Process Summary

### 1. Data Loading

All CSV files were loaded into the notebook using Pandas. The training and test-related files were inspected to understand the structure of the dataset.

### 2. Exploratory Data Analysis (EDA)

Exploratory analysis was performed to understand:

- Dataset shape and column types
- Missing values
- Distribution of audience counts
- Theatre-wise audience behavior
- Date-wise trends
- Weekend and holiday effects
- Booking patterns from BookNow and CinePOS

### 3. Data Preprocessing

The preprocessing steps included:

- Handling missing values
- Converting date columns into proper datetime format
- Creating useful date-based features
- Merging theatre information with booking and visit data
- Aggregating booking data at theatre and date level
- Preparing training and testing datasets

### 4. Feature Engineering

Several features were created to improve model performance, such as:

- Day of week
- Month
- Weekend indicator
- Holiday indicator
- Historical booking counts
- Theatre-level features
- Aggregated POS and online booking features
- Lag-based or rolling audience features where applicable

### 5. Model Building

Machine learning models were trained to predict audience counts. The models were evaluated using validation data before generating predictions for the test dataset.

Possible models used:

- Linear Regression
- Random Forest Regressor
- Gradient Boosting Models
- XGBoost / LightGBM if available

### 6. Prediction and Submission

After model training, predictions were generated for the test data. The final output was prepared in the same format as `sample_submission.csv`.

Final submission columns:

ID,audience_count
book_theater_001_2024-01-01,120
book_theater_002_2024-01-01,85


Conclusion

This project demonstrates the use of machine learning and time-series forecasting techniques to predict cinema audience attendance. By combining online booking data, POS booking information, theatre metadata, and date-based features, the model aims to capture audience demand patterns and produce accurate future attendance predictions.

Future Improvements
Use advanced time-series models
Add lag and rolling window features
Tune hyperparameters for better accuracy
Compare multiple models using cross-validation
Improve feature engineering using theatre location and booking trends
Use ensemble models for stronger predictions
