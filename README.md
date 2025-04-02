# SUPPORT2 Dataset Analysis
## Dataset Overview
- **Name**: SUPPORT2 (Study to Understand Prognoses and Preferences for Outcomes and Risks of Treatments)
- **Source**: UCI Machine Learning Repository: [https://archive.ics.uci.edu/dataset/880/support2]
- **Creator**: Frank Harrel, Department of Biostatistics, Vanderbilt University
- **Instances**: 9,105
- **Features**: 42
- **Subject Area**: Life Science
- **Associated Tasks**: Classification, Regression, Other
- **Time Range**: 1989-1994
  - Phase I: 1989-1991 (Observational study)
  - Phase II: 1992-1994 (Controlled clinical trial)
- **Funding**: Robert Wood Johnson Foundation
- **Missing Values:** There are recommended imputation values for certain variables, with details available here.
- **Introductory Paper:** A controlled trial to improve care for seriously ill hospitalized patients: [https://pubmed.ncbi.nlm.nih.gov/7474243/]

### Citation

Harrel, Frank. (2023). SUPPORT2. UCI Machine Learning Repository. https://doi.org/10.3886/ICPSR02957.v2

### Acknowledgements

Vanderbilt University Department of Biostatistics, Professor Frank Harrell 2022. https://hbiostat.org/data/

----------------------------------
------------------------------------
-------------------------------
---------------------------------
# Introduction
**Objective**: To explore the SUPPORT2 dataset to understand patient outcomes, healthcare resource utilization, and end-of-life care decisions.

**Approach**: Data quality assessment, exploratory data analysis (EDA), and survival analysis.

**Themes**:
- Patient Demographics
- Clinical Characteristics
- Socioeconomic Factors
- End-of-Life Care Decisions
- Survival Analysis

## Data Quality Assessment and Preprocessing
- **Handling NaN Values**: Imputation of missing values in categorical columns based on their missing percentage.
- **Numerical Imputation**: Using missingness and correlation heatmaps.
- **Feature Engineering**: Creating new features such as age groups.

### Missingness Heatmap

![image](https://github.com/user-attachments/assets/8fd91801-8533-4e65-8d68-31b8d958b2d5)

-----------------------------------
## Exploratory Data Analysis (EDA)
- **Chi-Square Test for Independence**: To find significant associations between categorical variables.

### Chi-square Test Results

| Test                        | Statistic  | P-Value |
|-----------------------------|------------|---------|
| Sex and DNR                 | 37.2       | 0.0000  |
| Age Group and DNR           | 316.9      | 0.0000  |
| DNR and Death               | 1299.8     | 0.0000  |
| Disease Group and Death     | 719.5      | 0.0000  |
| Age Group and Disease Group | 847.4      | 0.0000  |
| Race and Disease Group      | 133.6      | 0.0000  |
| Sex and Disease Group       | 78.9       | 0.0000  |
| Income and Death            | 204.9      | 0.0013  |

*The results show important associations with these categorical variables which guides decision-making and improve data interpretation.*

-------------------------
# Visusalisation Of Key Findings

## Theme 1:  Demographics and End-of-Life Care

#### DNR Status Across Sex and Age
![image](https://github.com/user-attachments/assets/f25a599a-da6c-4fcc-a134-94b41ccfb6e5) 

*These patterns confirm the Chi-Square results, highlighting that age is a stronger predictor of DNR decisions than sex, with older individuals more likely to opt for end-of-life care directives.*

-------------------

#### Income Across Cancer Status and Death
![image](https://github.com/user-attachments/assets/45f284ef-2fc0-4188-8729-6a360e277f69)

- **Income vs. Cancer Status:** *Lower-income groups have more cancer cases, while higher-income groups have fewer.*
- **Income vs. Death:** *Higher mortality in lower-income groups, fewer deaths in higher-income groups.*
--------------------------

#### Age Distribution
![image](https://github.com/user-attachments/assets/3a88221f-5f8d-407d-89d5-ebd8ac244c8c)

*The histogram shows that between the ages of 60 and 80 have the highest frequency of patients.*

------------------------

#### Age vs. Length of Stay
![image](https://github.com/user-attachments/assets/c5552127-2cc1-477b-9fd2-4cf91984e042) 

*Older patients (60 and 80 years) have longer stays in the hospital than other age groups.*

----------------------------------------

#### DNR Decision Timing
![image](https://github.com/user-attachments/assets/cb8ef746-9c5c-47c5-8768-fea7405b68be)

*Most people made DNR decisions after admission, reflecting situational or clinical judgment.*

-----------------------------

#### Age vs. Mortality
![image](https://github.com/user-attachments/assets/b7e3632e-17ff-4511-aaa9-042ba1114c34)

*The upper cluster indicates that patients who passed away are more likely to be older, while the lower cluster represents patients who survived.*

----------------
------------------

### Clinical and Mortality Rate

#### Death Across DNR and Disease Group
![image](https://github.com/user-attachments/assets/2503e06f-eb1d-4471-9e3a-6ec688ab1a17)

- **DNR Status vs. Death:** *Higher survival with "No DNR"; higher mortality with "DNR after SADM" and "DNR before SADM.*
- **Disease Group vs. Death:** *Highest mortality in Coma, ARF/MOSF with Sepsis, and MOSF with Malignancy; more balanced outcomes in Lung Cancer and Cirrhosis.*

Both DNR status and the type of disease significantly impact mortality, providing insights for clinical and end-of-life care planning.

-------------------------------------

#### Correlation Analysis
#### Correlation Heatmap of Selected Numerical Variables
![image](https://github.com/user-attachments/assets/40a0640d-0d95-4253-8c73-5a9e5bbfb681)

*Longer hospital stays and higher charges are strongly associated with increased total costs, while prolonged stays negatively impact 6-month survival probabilities. Illness severity scores (APS and SPS) show a strong correlation (0.80), indicating alignment between scoring systems in measuring patient severity.*

------------------------------

#### Mean Blood Pressure vs. Heart Rate
![image](https://github.com/user-attachments/assets/093b9352-8da0-4436-921d-b572cbd90b10)

*There is no visible linear relationship between blood pressure and heart rate, suggesting that they do not strongly depend on each other.*

--------------------------------

#### Charges by DNR Status
![image](https://github.com/user-attachments/assets/0b254e56-d012-4fd1-9780-f8de37cbee30)

*Patients without a DNR order typically have more varied and often higher medical charges. Patients with a DNR order before admission generally have lower medical charges.*

------------------------

#### APS vs. Mortality
![image](https://github.com/user-attachments/assets/c5dec745-d904-4259-9fa2-72e15a5b1f0e)

*Patients with higher APS values are more likely to die. The top plot shows that mortality increases with a high APS, while survival is concentrated in lower APS ranges.*

-----------------------

### Clinical Characteristics and Health Status
#### SUPPORT Score vs APACHE III Score
![image](https://github.com/user-attachments/assets/b759d7ed-fe38-40cf-bd2a-833e38f5309b)

*A strong positive linear relationship exists between these illness scores, indicating similar measures of illness severity.*

----------------------------

#### Severity Score vs. Disease Group
![image](https://github.com/user-attachments/assets/f868f2e9-ba7e-49cc-8b75-417678a8f186)

*Highest severity scores are seen in MOSF w/Malignancy, ARF/MOSF w/Sepsis, and Coma. Lowest severity scores are in Colon Cancer and Lung Cancer. Disease type heavily influences the severity of patients' health status.*

--------------------------------
----------------------------
## Survival Analysis

#### Survival Time by Disease Group
![image](https://github.com/user-attachments/assets/fff97bec-31e2-4cb4-abc3-89689e191e45)

*Chronic conditions like CHF and COPD show better long-term survival compared to aggressive diseases like Coma and MOSF w/Malignancy.*

--------------------------------
#### 6-Month Survival Probability by Disease Group
![image](https://github.com/user-attachments/assets/0e639b22-80d3-4e20-a13b-95deaaac673a)

*Higher median survival probabilities are seen in CHF and COPD, while lower median survival probabilities are seen in MOSF w/Malignancy and Coma.*

----------------------------
--------------------------
---------------------------
------------------------

## Conclusion and Summary

- **Data Quality**: The analysis involved robust imputation techniques and feature engineering, significantly improving data quality and reliability.
- **Key Findings**:
  - **Significant Associations**: Chi-square tests revealed significant associations between various categorical variables, such as age and DNR status, disease group and mortality, and income and healthcare outcomes.
  - **Predictors of DNR Decisions**: Age was identified as a stronger predictor of DNR decisions compared to sex, with older individuals more likely to opt for end-of-life care directives.
  - **Impact of Disease Type**: Disease type significantly influenced mortality rates and survival probabilities, with chronic conditions like CHF and COPD showing better long-term survival compared to aggressive diseases like Coma and MOSF w/Malignancy.
  - **Healthcare Resource Utilization**: Longer hospital stays and higher medical charges were associated with increased total costs and lower 6-month survival probabilities. Illness severity scores (APS and SPS) showed strong correlations, indicating their reliability in measuring patient severity.
- **Clinical Insights**: The insights gained from this analysis can guide clinical and policy decisions, particularly in understanding patient outcomes, optimizing healthcare resource utilization, and making informed end-of-life care decisions.


---------------------------
# THANK YOU

-----------------
