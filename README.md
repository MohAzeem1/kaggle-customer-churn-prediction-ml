Customer Churn Prediction using Machine Learning
Project Overview

Customer churn prediction is a crucial problem for companies that want to retain their customers. This project aims to build a machine learning model that predicts whether a customer will leave a service or continue using it.

In this project, a Random Forest Classifier is used to analyze customer data and predict churn based on multiple features such as tenure, monthly charges, services used, and customer demographics.

The model was trained and evaluated using a dataset provided in a Kaggle competition.

Dataset

The dataset used in this project comes from the Kaggle competition:

Predict Customer Churn – Playground Series (Season 6 Episode 3)

It contains customer information including:

Customer demographics

Services subscribed

Account information

Billing details

Customer churn status

The dataset consists of both training data and test data.

Target Variable

Churn

1 → Customer leaves the service

0 → Customer stays with the service

Technologies Used

Python was used as the main programming language along with the following libraries:

Pandas – Data manipulation and preprocessing

NumPy – Numerical operations

Scikit-learn – Machine learning algorithms

Matplotlib – Data visualization

Seaborn – Statistical data visualization
1 Data Loading

The dataset was loaded using Pandas and basic inspection was performed to understand the structure of the data.

Example:
train = pd.read_csv("train.csv")
test = pd.read_csv("test.csv")
2 Exploratory Data Analysis (EDA)

Several exploratory steps were performed including:

Checking missing values

Understanding feature distributions

Visualizing churn distribution

Analyzing the relationship between churn and other variables

Example visualization:
sns.countplot(x='Churn', data=train)
plt.show()
3 Data Preprocessing

The dataset contained categorical variables that needed to be converted into numerical form.

Label Encoding

The target variable was converted into numeric form.
train['Churn'] = train['Churn'].map({'Yes':1,'No':0})
One-Hot Encoding

Categorical variables were converted into dummy variables using:
train = pd.get_dummies(train)
test = pd.get_dummies(test)
This ensures that machine learning algorithms can process the data effectively.

4 Feature and Target Separation

The dataset was divided into:

Features (X) – Input variables

Target (y) – Churn variable
X = train.drop('Churn', axis=1)
y = train['Churn']
5 Train Test Split

The training data was split into training and validation sets to evaluate model performance.
from sklearn.model_selection import train_test_split

x_train, x_valid, y_train, y_valid = train_test_split(
    X, y, test_size=0.2, random_state=42
)
6 Model Training

A Random Forest Classifier was used for prediction.

Random Forest is an ensemble learning method that builds multiple decision trees and combines their predictions.
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier(
    n_estimators=100,
    random_state=42,
    n_jobs=-1
)

model.fit(x_train, y_train)
7 Model Evaluation

The model performance was evaluated using accuracy score.
from sklearn.metrics import accuracy_score

y_pred = model.predict(x_valid)
accuracy = accuracy_score(y_valid, y_pred)

print("Validation Accuracy:", accuracy)
Validation Accuracy Achieved:

0.84

8 Prediction on Test Data

The trained model was used to generate predictions on the unseen test dataset.
test_pred = model.predict(test)
9 Submission File Creation

A submission file was generated in the required Kaggle format.
submission = pd.DataFrame({
    "id": pd.read_csv("sample_submission.csv")["id"],
    "Churn": test_pred
})

submission.to_csv("submission.csv", index=False)
Kaggle Result

Public Leaderboard Score:

0.74553

This score placed the submission on the Kaggle leaderboard for the competition.
Customer-Churn-Prediction
│
├── predict_customer_churn.ipynb
├── submission.csv
├── requirements.txt
└── README.md
Installation

To run this project locally:
git clone https://github.com/yourusername/customer-churn-prediction.git
cd customer-churn-prediction
pip install -r requirements.txt
Then open the notebook:
jupyter notebook
Future Improvements

Possible improvements for better performance:

Feature engineering

Hyperparameter tuning

Cross-validation

Trying advanced models such as:

XGBoost

LightGBM

CatBoost

These techniques could significantly improve prediction accuracy.

Author

Moh Azeem

B.Tech Computer Science Engineering
Machine Learning and Data Analytics Enthusiast
Jupyter Notebook – Development environment

Project Workflow
