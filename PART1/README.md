Smoking Intensity Prediction with Random Forest
Overview
This project applies machine learning techniques to classify individuals into different smoking intensity levels based on survey data. By leveraging Random Forest Classifiers, we analyze feature importance, optimize the model, and explore the impact of feature reduction.

Project Goals
Predict smoking intensity levels:
0: 10 or less cigarettes/day
1: 11 to 20 cigarettes/day
2: 21 to 30 cigarettes/day
3: 31 or more cigarettes/day
Understand the importance of features in the dataset.
Compare the performance of models trained on:
All features.
Only the top 10 most significant features.
Steps Taken
1. Data Loading
The dataset was sourced from Google Sheets and loaded into the environment using a CSV export link.
2. Data Cleaning
Removed unnamed and duplicate columns for a cleaner dataset.
3. Data Preprocessing
Target Encoding: Smoking intensity was mapped to numerical classes:
"10 or less cigarettes/day" → 0
"11 to 20 cigarettes/day" → 1
"21 to 30 cigarettes/day" → 2
"31 cigarettes/day or more" → 3
One-Hot Encoding:
Categorical variables were transformed into binary features.
Example: "Employment Status" → Employment Status_Employed, Employment Status_Unemployed, etc.
Scaling: Numerical features were standardized using z-score scaling for better model performance.
4. Model Training
Trained a Random Forest Classifier using all features.
Analyzed feature importance to identify the most impactful predictors.
5. Feature Reduction
Selected the top 10 features based on feature importance.
Retrained the model using only these features.
6. Evaluation and Comparison
Evaluated both models (original and retrained) on the test set using:
Accuracy
Precision
Recall
F1-Score
Visualized predictions and performance with:
True vs. Predicted Class Plots
Confusion Matrices
Results
Metric	Original Model	Retrained Model
Accuracy	62.79%	58.14%
Precision	61.95%	60.73%
Recall	62.79%	58.14%
F1-Score	59.91%	58.62%
Observations:
Original Model performed better overall.
Feature reduction simplified the model but led to a slight drop in performance.
Conclusion
Random Forest may not be the best-suited algorithm for this problem.
Alternative approaches like Gradient Boosting Machines (e.g., XGBoost, LightGBM) or neural networks should be explored.
Feature engineering and hyperparameter tuning could further improve performance.
