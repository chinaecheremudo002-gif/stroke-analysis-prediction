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
The dataset contains [5110] rows and [12] columns. Initial checks for missing values, correct data types, and valid ranges for numerical and binary variables ensured the data were ready for analysis.

Building on this understanding, I conducted Exploratory Data Analysis (EDA) to uncover patterns and relationships among patient features and stroke occurrence. EDA helped identify key predictors, correlations, and imbalances in the dataset, guiding feature selection, preprocessing, and model development. I began by examining age, followed by medical conditions and lifestyle factors, to understand how each contributes to stroke risk.

# STROKE RATE ANALYSIS BY AGE GROUP
Stroke is rare in individuals under 40 (<1%). Still, risk rises sharply after 50, peaking at 18% in those aged 70 and above, with elders accounting for over half (51%) of all stroke cases, making age a major risk factor and highlighting the importance of focusing prevention efforts on adults aged 50 and older.
 <img width="7169" height="5305" alt="age_rate" src="https://github.com/user-attachments/assets/3aff0ff7-2221-4592-b8bb-7ddc02a38156" />



# STROKE RATE ANALYSIS BY SMOKING STATUS
## Stroke and Smoking: Key Insights
Former smokers have the highest stroke rate at 7.9%, higher than current smokers (5.3%). They tend to be older (average age 55) and have the highest rates of hypertension (13.6%) and heart disease (8.7%), suggesting many quit after health complications have already developed.
Current smokers also show elevated risk (~5.3%, average age 47), while never smokers have lower individual risk (~5%) but contribute the most total strokes (36%) because this is the largest group.
The Unknown group has the lowest stroke rate (3%), explained by younger age (average 30), not any protective effect.
Age is the dominant driver: in a heatmap of stroke by age and smoking status, elders (70+) have a 17% stroke rate across all smoking categories. Within each age group, differences between smoking statuses are minor.
## Gender differences:
Former smokers: males 8.85%, females 7.13%
Never smoked: females 5.13%, males 4.07%
Current smokers: males 6.82%, females 4.02%
Takeaway: Age drives stroke risk; smoking amplifies it but is not the primary cause. Population size and comorbidities also affect total stroke counts.
<img width="7169" height="5309" alt="smoke_rate" src="https://github.com/user-attachments/assets/50ad3c82-fe0a-4531-b427-848f789614d2" />

# HYPERTENSION AND STROKE RISK
Hypertension shows a strong relationship with stroke occurrence. Patients without hypertension have a stroke rate of 3.97%, while those with hypertension show a much higher rate of 13.25%, representing about a 3.3× increase in risk.

Age appears to play an important role. The average age of non-hypertensive individuals is 41 years, compared with 62 years among hypertensive patients. Since stroke risk increases with age, this age gap likely contributes to the higher stroke rate observed in the hypertensive group.

Other health indicators further highlight the risk. Hypertensive patients show higher average glucose levels (130 mg/dL) and a higher BMI (32.57), placing them in the obese category. In contrast, non-hypertensive individuals have lower glucose levels and fall within the overweight range.

These findings suggest that hypertension is part of a broader cardiometabolic risk profile involving age, obesity, and impaired glucose control.
# HEART DISEASE AND STROKE RISK
An even stronger pattern appears with heart disease. Individuals without heart disease have a stroke rate of 4.18%, while those with heart disease show a much higher rate of 17.03%, nearly a fourfold increase in risk.

Age differences are again substantial. The average age of individuals without heart disease is 41.8 years, compared with 68.2 years for those with heart disease. This older population is naturally more vulnerable to vascular damage and stroke.

Patients with heart disease also exhibit higher glucose levels (136 mg/dL) and an average BMI of 30, placing them in the obese category. These metabolic factors further increase cardiovascular risk.

## Key Insight
The analysis reveals a clear cardiometabolic pattern. Patients with hypertension or heart disease tend to be older, heavier, and show higher glucose levels. Among these conditions, heart disease appears to be the strongest predictor of stroke in this dataset.

While age may act as a confounding factor, the results highlight that individuals with hypertension and especially heart disease represent high-risk populations for stroke.
<img width="6196" height="4708" alt="hyper_rate" src="https://github.com/user-attachments/assets/bb921015-fa01-4333-97a5-e8b9dfd4259c" />



