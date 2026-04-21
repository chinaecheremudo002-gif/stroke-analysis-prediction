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

EVER MARRIED & WORK TYPE vs STROKE
Ever Married and Stroke Risk
Marital status shows noticeable differences in stroke occurrence.

Married individuals have a stroke rate of 6.56%, compared with 1.65% among unmarried individuals, representing nearly a fourfold increase in risk. Married individuals also account for 88.35% of all stroke cases, while unmarried individuals contribute only 11.65%.

However, the primary explanation appears to be age. The average age of married individuals is 54.34 years, whereas unmarried individuals average only 22.01 years. Since stroke risk increases with age, this age gap likely drives much of the difference.

Other health indicators also show elevated risk among married individuals. Their average BMI is 30.73, placing them in the obese category, while unmarried individuals average 25.30, within the overweight range. Average glucose levels are also slightly higher among married individuals (111.23 mg/dL) compared with unmarried individuals (96.45 mg/dL), though both remain below diabetic thresholds.

Overall, the higher stroke rate observed among married individuals is largely associated with older age, higher BMI, and slightly elevated glucose levels.
<img width="6196" height="4708" alt="hyper_rate" src="https://github.com/user-attachments/assets/bb921015-fa01-4333-97a5-e8b9dfd4259c" />

# WORK TYPE AND STROKE RISK
Stroke risk also varies across work types, largely reflecting differences in age and lifestyle.

Self-employed individuals show the highest stroke rate (7.94%), with an average age of 60 years, indicating that age is a major driver of risk in this group.

Government workers and private sector employees show similar stroke rates of around 5%, with average ages of 50.9 and 45.5 years, respectively. Private sector workers account for the largest share of strokes (59.84%), mainly because this group represents the largest portion of the dataset.

In contrast, individuals who have never worked and children show almost no stroke risk. Their average ages are 16 years and 6.8 years, respectively, explaining their extremely low stroke occurrence.

Across most working groups, BMI values are around 30, indicating obesity, which may further increase cardiovascular risk.

## Key Insight
The analysis shows that stroke risk is strongly age-dependent. Groups with older average ages, such as the self-employed, government workers, and married individuals, exhibit higher stroke rates. While glucose levels remain mostly within safe ranges, elevated BMI and aging appear to amplify stroke risk across multiple demographic groups.
<img width="6111" height="4706" alt="work type _rate" src="https://github.com/user-attachments/assets/9ed12b11-5ec5-4293-a45d-7430cb0cb73c" />

# RESIDENCE TYPE VS STROKE
Analysis of stroke metrics across residence types reveals notable patterns. Urban residents exhibit a slightly higher stroke rate of 5.20% compared to 4.53% among rural residents, contributing 54.22% of total strokes versus 45.78% from rural areas. Despite this difference in stroke prevalence, the average glucose levels and BMI are virtually identical between urban and rural populations, measuring 105.93 vs. 106.38 for glucose and 28.86 for BMI in both groups. The average age is marginally higher in urban residents (43.54 years) than in rural residents (42.90 years).

Residence type is confirmed as the weakest predictor in the entire dataset alongside gender. With a stroke rate difference of only 0.67%, virtually identical average ages, glucose levels, BMI, hypertension rates and heart disease rates between urban and rural patients, residence type adds absolutely no independent predictive value to the model. Dropping it from the model is not only correct but necessary to keep the model clean and free of noise features.
<img width="5563" height="4120" alt="residence type _rate" src="https://github.com/user-attachments/assets/972515b2-21cb-49f9-bda3-1ed1fabc7b6a" />

# BMI AND STROKE
## Key Insights
Stroke rates across BMI categories are inconsistent. Underweight patients have the lowest rate (0.29%) due to young age, while Overweight and Obese patients sit around 5%, and Extremely Obese patients surprisingly drop to 4.41%. This non-linear pattern shows that BMI alone is a weak predictor.

Distribution overlap confirms this: stroke and non-stroke patients share nearly identical BMI ranges, with average BMIs of 30.47 and 28.82, respectively. Any model relying on BMI struggles to separate the two groups.

Age is the real driver. Stroke rates rise with age, closely matching the increase in BMI, meaning what appears as a BMI effect is largely age-related.

BMI influences stroke risk indirectly. Higher BMI correlates with elevated glucose and increased hypertension, creating conditions that raise stroke risk rather than directly predicting it.

## Takeaway: BMI alone cannot predict stroke. Its effect is indirect, operating through age, glucose, and hypertension. Removing it from models can even improve predictive performance.
<img width="5964" height="2956" alt="bmi type _rate" src="https://github.com/user-attachments/assets/2ac7d7b2-7bd8-4191-9926-e99bdf66d099" />

# GLUCOSE AND STROKE
## Key Insights
Glucose is a clear and strong predictor of stroke. Stroke rates remain low below 150 mg/dL, but once glucose exceeds 150, risk jumps dramatically. Very High patients have a rate of 11.49 percent and Diabetic patients reach 12.90 percent. This threshold effect makes glucose clinically significant.

Stroke patients average 132.54 mg/dL compared to 104.80 mg/dL for non-stroke patients, creating a 27-point mean gap. This meaningful separation, especially above 150, allows models to reliably distinguish stroke risk, unlike BMI, which overlaps heavily.

Volume effects matter. The Normal group contributes many strokes due to size, while the Diabetic group contributes fewer strokes but has a high individual risk. Age explains part of the trend at extreme glucose levels, but the magnitude of the jump above 150 cannot be explained by age alone.

High glucose often coincides with hypertension and heart disease, creating a compounding risk profile.

## Takeaway: Glucose is one of the strongest independent predictors of stroke in this dataset. Its sharp threshold effect and clear separation between stroke and non-stroke patients make it essential for any predictive model.

# GLUCOSE AND STROKE
## Key Insights
Glucose is a clear and strong predictor of stroke. Stroke rates remain low below 150 mg/dL, but once glucose exceeds 150, risk jumps dramatically. Very High patients have a rate of 11.49 percent and Diabetic patients reach 12.90 percent. This threshold effect makes glucose clinically significant.

Stroke patients average 132.54 mg/dL compared to 104.80 mg/dL for non-stroke patients, creating a 27-point mean gap. This meaningful separation, especially above 150, allows models to reliably distinguish stroke risk, unlike BMI, which overlaps heavily.

Volume effects matter. The Normal group contributes many strokes due to size, while the Diabetic group contributes fewer strokes but has a high individual risk. Age explains part of the trend at extreme glucose levels, but the magnitude of the jump above 150 cannot be explained by age alone.

High glucose often coincides with hypertension and heart disease, creating a compounding risk profile.

## Takeaway: Glucose is one of the strongest independent predictors of stroke in this dataset. Its sharp threshold effect and clear separation between stroke and non-stroke patients make it essential for any predictive model.
<img width="5972" height="4724" alt="glucose type _rate" src="https://github.com/user-attachments/assets/36614ebb-de0a-4f50-8dd1-274c69ee95d4" />

# MULTIVARIATE STROKE RISK: WHEN FACTORS CONVERGE
The real stroke story emerges when multiple risk factors intersect. Plotting age against glucose and coloring by stroke status reveals that high-risk patients cluster in the top-right corner, older individuals with elevated glucose. Young patients with low glucose are almost entirely at low risk, showing that neither age nor glucose alone tells the full story. Stroke becomes truly dangerous when these two factors converge.

Adding hypertension to the picture highlights another layer of risk. Hypertensive patients cluster among older adults but appear across all glucose levels. This confirms that hypertension carries an independent stroke risk, not solely explained by age or glucose.

Heart disease patients show an even more concentrated risk. They cluster in older age ranges but span the full glucose spectrum. Unlike glucose, which only becomes dangerous above 150 mg/dL, heart disease elevates stroke risk at every glucose level, making it the strongest single binary predictor with a 17.03 percent stroke rate.

Subscribe to the Medium newsletter
The combined effect of cardiovascular conditions is alarming. Patients with neither hypertension nor heart disease have a stroke rate of 3.39 percent. Adding hypertension alone raises it to 12.21 percent, heart disease alone to 16.04 percent, but having both simultaneously jumps the rate to 20.31 percent. The risks multiply rather than simply add, creating a compounding effect that highlights extreme vulnerability.

## Takeaway: Stroke risk is not a single-feature problem. It is a convergence problem. Patients at the intersection of old age, elevated glucose above 150, and one or both cardiovascular conditions face dramatically higher risk. This is why predictive models must include age, glucose, hypertension, heart disease, and smoking status together. Only by considering all pathways simultaneously does the true stroke story emerge.
<img width="7472" height="5896" alt="multi  type _rate" src="https://github.com/user-attachments/assets/12340683-5f8f-47de-9b74-ef31daf1a86f" />

# CORRELATION HEATMAP INSIGHTS
The correlation heatmap reveals key relationships in the dataset. Every cell along the diagonal shows 1.00, which is expected, as each feature perfectly correlates with itself.

Looking at the correlation with stroke, age leads with 0.25, followed by average glucose level, heart disease, and hypertension, all around 0.13. Ever married contributes 0.11, smoking status 0.07, BMI 0.04, residence type 0.02, and gender 0.01. This confirms that age is the strongest predictor, while gender and residence provide almost no information on stroke risk.

The most important feature-to-feature relationship is between age and ever married, which correlates at 0.45, the highest off-diagonal value. This mathematically confirms that ever married is mostly a proxy for age. Including both could confuse models by feeding redundant information, making dropping ever married the right decision.

The correlation values may seem low overall, but this is expected. Correlation measures linear relationships, and stroke risk is highly non-linear. Younger age groups and minors rarely experience stroke, while risk rises sharply after 40. Combined with the dataset’s class imbalance, even strong predictors like age or glucose appear only moderately correlated numerically.

Ultimately, a correlation of 0.25 for age does not imply weakness. It is a reflection of non-linear risk patterns and imbalanced data rather than a lack of predictive power. Age, glucose, heart disease, and hypertension remain the most meaningful signals for stroke prediction.
<img width="5564" height="5368" alt="corre type _rate" src="https://github.com/user-attachments/assets/49ca2055-192c-468c-a9dc-d2089d8aa129" />

# FROM DATA EXPLORATION TO PREDICTIVE MODELING
With the exploratory analysis complete, we now move from understanding the data to predicting stroke risk. The EDA highlighted the most meaningful features, age, glucose, heart disease, and hypertension, and revealed how they interact to amplify risk. It also identified weaker or redundant features, such as BMI and ever married, which can be excluded from modeling.

Machine learning provides the tools to leverage these insights effectively. Unlike simple statistical analysis, ML can handle non-linear relationships, complex interactions, and imbalanced datasets. For example, the dramatic stroke risk increase above a glucose threshold of 150 or the compounding effect of age with cardiovascular conditions cannot be captured accurately with linear models alone.

This is where predictive modeling comes in. By feeding the selected features into algorithms such as Logistic Regression, Random Forest, or XGBoost, we aim to build a model that not only captures individual risk factors but also accounts for their combined effect, ultimately providing a more precise and actionable stroke risk prediction.

# CLASS IMBALANCE
The dataset is severely imbalanced with a 19.5:1 ratio. A naïve model predicting “no stroke” for every patient would achieve 95.13% accuracy without learning anything useful, confirming that accuracy is not an appropriate evaluation metric for this problem.

<img width="2119" height="1885" alt="count_rate" src="https://github.com/user-attachments/assets/9a8fe2e8-9f48-4f24-b40c-e43aa5e25f73" />

Class imbalance is a key issue in this dataset because stroke cases represent only a small fraction of the observations. In such situations, machine learning models tend to favor the majority class (non-stroke cases), which can produce deceptively high accuracy while failing to correctly identify stroke cases. To address this problem, SMOTE (Synthetic Minority Over-sampling Technique) was applied to generate additional synthetic samples for the minority class, helping balance the dataset during training. Class weighting was also used so that the model assigns greater importance to correctly predicting stroke cases.

Initially, there was concern that these techniques might lead to overfitting. However, cross-validation results and the model’s recall scores helped dispel this concern, indicating that the model was still able to generalize well while improving its ability to detect stroke cases.
















