# Cardiovascular-Disease-CVD-Risk-Analysis

## Table of contents
- [Project Overview](#project-overview)
- [Exploratory Analysis](#exploratory-analysis)
- [Recommendations](#recommendations)
- [Limitations](#limitations)
-   
##  Project Overview
This project uses Python to explore, clean, and model cardiovascular disease risk using a real-world patient dataset. The goal is to identify key risk indicators and predict the likelihood of cardiovascular disease (CVD) using logistic regression. it applies **exploratory data analysis**, **data visualization**, and **logistic regression modeling** to a real-world dataset to:
- Understand risk factors behind CVD.
- Uncover trends related to age, gender, and lifestyle.
- Build a predictive model that flags high-risk patients.
- Present findings suitable for both data scientists and healthcare teams.
  

  ##  Tools & Technologies

| Category           | Stack Used                         |
|--------------------|------------------------------------|
| Programming        | Python (Pandas, NumPy)             |
| Visualization      | Seaborn, Matplotlib                |
| Machine Learning   | Scikit-Learn (Logistic Regression) |
| Data Preprocessing | StandardScaler                     |
| Modeling Metrics   | Accuracy, Precision, Recall, F1    |



## 🧹 Data Preprocessing

- Converted `age` from days to years for interpretability.
- Mapped gender from numeric (1/2) to text (female/male).
- Filtered out extreme blood pressure outliers (e.g., systolic > 200).
- Created derived features: `Age Group`, High Risk Flag.
- Handling missing values.

```python
df['age'] = (df['age'] / 365).astype(int)
df.head()
```
```python
df_cleaned['gender'] = df_cleaned['gender'].map({1: 'female', 2: 'male'})
df_cleaned.head()
```


📁 Dataset used: https://www.kaggle.com/datasets/sulianova/cardiovascular-disease-dataset

##  Exploratory Analysis

## Analysis

- CVD correlated with **systolic BP > 130**, **age > 50**, and **cholesterol level 3**
- Gender differences were minimal, but women had slightly higher CVD count (due to sample size)
- Patients with CVD are older, heavier, and have significantly higher blood pressure, cholesterol, and glucose levels.
-  Both genders are equally affected by CVD, but women form a slightly larger portion of the sample.
-  CVD risk increases significantly with higher cholesterol levels.
-  Physical activity is slightly higher in the non-CVD group. Surprisingly, smoking and alcohol rates are slightly lower in CVD patients likely due to lifestyle changes after diagnosis.

## 🎯 High-Risk Profile/findings
Based on the data, high-risk individuals are:
-	Aged 55 and above.
-	With high cholesterol (level 3) and glucose levels above normal.
-	Showing elevated blood pressure (above 130/85 mmHg).
-	Often overweight or obese.
-	Less likely to be physically active.

## 📈 Model Building: Logistic Regression

### Model Inputs:
- Features: Age, Gender, BP, Cholesterol, Glucose, Lifestyle
- Target: `cardio` (1 = has CVD, 0 = no CVD)

### Performance:
| Metric      | Score     |
|-------------|-----------|
| Accuracy    | 72.5%     |
| Precision   | 75%       |
| Recall      | 67%       |
| F1 Score    | 71%       |

✅ Balanced results — great for early warning systems

##  Recommendations
## For Healthcare Administrators:
-	Launch preventive screening programs targeting individuals over age 50 with elevated cholesterol or BP.
-	Introduce nutrition and exercise counseling for high-risk groups.


## For Insurance Partners:
-	Use cholesterol, age, and blood pressure as premium-adjustment criteria.
- Offer discounts for maintaining healthy lifestyle behaviors (verified through health checkups).

## For Medical Teams:
-	Flag patients with high cholesterol and BP as priority cases.
-	Encourage follow-ups with inactive patients or those with poor glucose control.

## 🧪 For Medical Research & Policy
- Investigate the underlying causes of high CVD prevalence in patients with normal glucose but elevated cholesterol — a strong pattern in the data.
- Use this model as a baseline risk stratification tool in government-funded health screenings.

##  Limitations
While this analysis provides valuable insights and a predictive baseline, several limitations should be considered:

📉 1. Lack of Time-Based Data
The dataset lacks timestamps (e.g., diagnosis date, checkup frequency), preventing time-series analysis or progression tracking of patient health over time.

📦 2. Binary Outcome
The cardio target is binary (1 = has CVD, 0 = doesn't), which does not capture:
- Severity or type of CVD
- Stages of disease progression

🧪 3. Limited Medical Variables
Key health indicators such as:
- HDL/LDL cholesterol
- Triglycerides
- Family history
- Stress levels
- Medication history
...are missing, which could improve prediction accuracy and clinical relevance.

🌍 4. No Socioeconomic or Regional Context
There is no information on region, income, education, or dietary habits, which are known social determinants of cardiovascular health.











