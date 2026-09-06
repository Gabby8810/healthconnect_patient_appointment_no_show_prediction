# HealthConnect Patient Appointment No-Show Prediction

## Project Overview

This project was developed as part of the **AnalystLab Africa Experience Lab** under the HealthConnect Clinic project.

The project applies data science and machine learning techniques to predict patient appointment attendance using historical appointment data. The objective is to identify appointments at risk of resulting in a no-show and support interventions such as reminders and follow-up.

---

## Problem Statement

Missed appointments can reduce the efficient use of healthcare resources and appointment slots. This project investigates whether historical appointment data can support the development of a machine-learning model for predicting patient attendance.

The problem was formulated as a supervised binary classification task.

---

## Machine Learning Objective

**Target Variable:** `no_show`

| Value | Outcome  |
| ----- | -------- |
| 0     | No-Show  |
| 1     | Attended |

Cancelled appointments were excluded because cancellation represents a different outcome from both attendance and no-show behaviour.

After removing cancelled appointments, the final modelling dataset contained **4,737 appointment records**.

---

## Data Preparation

The dataset was prepared through the following steps:

* Missing value assessment and treatment
* Duplicate record checks
* Categorical variable consistency checks
* Date format conversion
* Treatment of cancelled appointments
* Target variable creation
* Data leakage assessment
* Feature engineering
* Categorical feature encoding

Identifier variables such as `appointment_id` and `patient_id` were excluded from direct model input to reduce irrelevant patterns and potential overfitting.

---

## Exploratory Data Analysis

Exploratory analysis was conducted to examine:

* Appointment outcome distribution
* Numerical feature distributions
* Feature-outcome relationships
* Previous appointment behaviour
* Potential outliers and data patterns

Visualisations were used to support feature selection and preprocessing decisions.

---

## Machine Learning Models

Three classification models were developed and evaluated:

1. Logistic Regression
2. Decision Tree Classifier
3. Random Forest Classifier

The models were evaluated using:

* Accuracy
* Precision
* Recall
* F1-Score
* ROC-AUC

Particular attention was given to **No-Show recall**, as identifying potential missed appointments is important for targeted interventions.

---

## Final Model

The **Decision Tree Classifier** demonstrated the strongest overall performance and was selected as the final model.

### Final Performance

* **Accuracy:** ~61%
* **No-Show Precision:** ~61%
* **No-Show Recall:** ~62%
* **No-Show F1-Score:** ~62%

The results indicate that the available appointment data contains useful predictive patterns. However, further feature development and data collection may be required to improve performance before operational deployment.

---

## Key Findings

* Cancelled appointments were excluded from the binary classification task.
* The final target was encoded as `0 = No-Show` and `1 = Attended`.
* The Decision Tree achieved the strongest performance among the evaluated models.
* Historical appointment data provides useful information for predicting attendance behaviour.
* The model should be considered a decision-support tool rather than a fully automated healthcare decision system.

---

## Recommendations

Future development could focus on:

* Additional feature engineering
* Advanced model experimentation
* Hyperparameter optimisation
* Classification threshold tuning
* Additional behavioural and appointment history variables
* Model monitoring using new data
* Development of a dashboard or user interface for healthcare staff

---

## Tools and Technologies

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Jupyter Notebook / Google Colab
* Git and GitHub

---

## Project Structure

```text
HealthConnect-No-Show-Prediction/
│
├── data/
│   └── HealthConnect_Final_Model_Dataset.csv
│
├── notebooks/
│   └── HealthConnect_No_Show_Prediction.ipynb
│
├── models/
│   └── healthconnect_no_show_model.pkl
│
├── README.md
└── requirements.txt
```

---

## Project Workflow

```text
Data Collection
      ↓
Data Quality Assessment
      ↓
Data Preprocessing
      ↓
Exploratory Data Analysis
      ↓
Feature Engineering
      ↓
Feature Encoding
      ↓
Train-Test Split
      ↓
Model Development
      ↓
Model Evaluation
      ↓
Model Comparison
      ↓
Final Model Selection
```

---

## Conclusion

This project demonstrates the application of a structured machine-learning workflow to predict patient appointment attendance. Among the evaluated models, the Decision Tree achieved the strongest performance, with approximately **61% accuracy** and **62% recall for No-Show appointments**.

Although the results demonstrate predictive potential, further data enrichment and model optimisation are required before practical deployment. The current model provides a foundation for a decision-support system that could help healthcare providers identify appointments requiring additional reminders or follow-up.

---

**Programme:** AnalystLab Africa Experience Lab
**Project:** HealthConnect Clinic
**Track:** Data Science
**Project Stage:** Week 5 – Data Preparation, Exploratory Analysis and Machine Learning Modelling
