1.Close Price Prediction:

Data Preprocessing & Feature Engineering:
Converts the Date column to datetime format and sets it as the index.
Creates rolling statistics such as Simple Moving Average (SMA) and Exponential Moving Average (EMA) for the 'Open' prices.
Generates lag features and computes the rate of change for 'Volume' to capture market trends.
Handles missing values using mean imputation and normalizes the features with StandardScaler.
Model Training & Evaluation:
Splits the data into training and validation sets.
Trains a LinearRegression model to predict the 'Close' prices.
Evaluates the model using Mean Absolute Error (MAE) and Symmetric Mean Absolute Percentage Error (sMAPE).

2.Strategy Recommendation (Buy, Hold, Sell):

Data Preprocessing & Feature Engineering:
Encodes the 'Strategy' column using LabelEncoder.
Creates additional lag features for both 'Open' and 'Close' prices.
Calculates the 20-day SMA for 'Close' prices.
Model Training & Evaluation:
Splits the data into training and testing sets.
Trains an ensemble of three XGBoost classifiers with varying hyperparameters.
Combines the classifiers using a VotingClassifier with soft voting to improve prediction accuracy.
Evaluates the ensemble model using accuracy metrics.
Prediction on Test Data:
Applies the same preprocessing and feature engineering steps to the test dataset.
Uses the trained ensemble model to predict the optimal trading strategies.
Prepares the final submission file with the predicted strategies.


How to Use
Environment Setup:

Ensure all required libraries are installed as listed in requirements.txt.
Data Preparation:

Place train.csv and test.csv in the designated data directory.
Running the Notebook:

Execute the notebook cells sequentially to perform data preprocessing, feature engineering, model training, evaluation, and prediction.
Results:

The notebook outputs evaluation metrics such as MAE, sMAPE for close price prediction, and accuracy for strategy recommendation.
Generates test.csv with predicted close prices and submission.csv with recommended trading strategies.
