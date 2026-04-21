# stroke-analysis-prediction

# INTRODUCTION
Stroke is a serious medical condition that occurs when the blood supply to the brain is interrupted, either by a blockage or a burst blood vessel. It is one of the leading causes of death and long-term disability worldwide. Early identification of people at high risk can help prevent strokes through lifestyle changes, medication, and regular monitoring.

# PROBLEM STATEMENT
According to the World Health Organization (WHO), stroke is the second leading cause of death globally, accounting for approximately 11% of total deaths. Despite its severity, healthcare providers often rely on manual risk assessment, which can overlook hidden patterns in patient data. Early identification of high-risk individuals is crucial for timely intervention and improved outcomes.

This project leverages healthcare data to enhance stroke diagnosis by developing machine learning models. By analyzing clinical and demographic features, it aims to identify individuals at high risk of stroke, supporting proactive medical intervention and preventive care.

# OBJECTIVES:
Analyze Patient Data: Explore demographic, lifestyle, and medical indicators to understand their relationship with stroke occurrence.

Preprocess the Data: Handle missing values, encode categorical variables, and address class imbalance in the dataset.

Develop Predictive Models: Build and train machine learning models to predict the likelihood of stroke in patients.

Create a Predictive Formula: Develop a formula where patient-specific variables (e.g., age, blood pressure, lifestyle factors) can be inputted to calculate an individual’s stroke risk.

Evaluate Model Performance: Compare models using metrics such as accuracy, precision, recall, F1-score, and AUC to select the best-performing approach.

# DATASET SOURCE
The data used in this project comes from the publicly available Stroke Prediction Dataset provided on Kaggle . It contains anonymized patient information, including demographics, lifestyle habits, and medical indicators, collected to study factors associated with stroke occurrence.
 <img width="1047" height="756" alt="data head" src="https://github.com/user-attachments/assets/55e0621a-be5e-48d6-b3d8-adfacbdb1fce" />

# Data Understanding and Exploratory Data Analysis (EDA)
Before building a predictive model for stroke risk, it is essential to understand the dataset and explore its characteristics. This dataset contains patient demographic, lifestyle, and medical information, with each row representing a patient and columns representing individual attributes. The variables include a mix of numerical, categorical, and binary types.

## Key Features:
## <img width="952" height="694" alt="A DATA VARIABLE " src="https://github.com/user-attachments/assets/de2caced-6dfa-4b90-b46e-55865d9c784c" />
