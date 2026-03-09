# Customer Churn Prediction

A Machine Learning project that predicts whether a customer will leave a service or continue using it.  
The model was trained using **Random Forest Classifier** and evaluated using validation accuracy.

---

## Dataset

Dataset used from Kaggle competition:

**Predict Customer Churn – Playground Series (Season 6 Episode 3)**

Features include:
- Gender
- SeniorCitizen
- Tenure
- InternetService
- Contract
- MonthlyCharges
- TotalCharges

Target Variable:

- **Churn = 1** → Customer leaves
- **Churn = 0** → Customer stays

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook

---

## Project Workflow

1. Data Loading  
2. Exploratory Data Analysis (EDA)  
3. Data Preprocessing  
4. One-Hot Encoding using `pd.get_dummies()`  
5. Train-Validation Split  
6. Model Training using Random Forest  
7. Model Evaluation  
8. Prediction on Test Data  
9. Kaggle Submission

---

## Model Used

**Random Forest Classifier**

Validation Accuracy: **0.84**

---

## Kaggle Result

Public Leaderboard Score:

**0.74553**

---

## Project Structure
Customer-Churn-Prediction
│
├── predict_customer_churn.ipynb
├── submission.csv
├── requirements.txt
└── README.md
