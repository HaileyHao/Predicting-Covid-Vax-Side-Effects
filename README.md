# Predicting-Covid-Vax-Side-Effects
![R](https://img.shields.io/badge/r-%23276DC3.svg?style=for-the-badge&logo=r&logoColor=white)


# Introduction 

This is a machine learning project for predicting self-reported Covid-19 Vaccine Side effect. I fit three supervised learning models to the reported COVID-19 Vaccine side effect data of 2021 in the United States from the CDC's Vaccine Adverse Event Reporting System (VAERS), to predict whether the patient recovered from the side effect. And in the end the random forest model with the highest prediction accuracy. 

# Data set: VAERS 2021 Data Set 

The data is a combination of the Covid-19 vaccine side effect data and COVID-19 vaccine manufacture information in 2021 collected by The Vaccine Adverse Event Reporting System (VAERS). The U.S. Department of Health and Human Services (DHHS) established VAERS, which is co-administered by the FDA and the CDC, to accept all reports of suspected adverse events, in all age groups, after the administration of any U.S. licensed vaccine.

- Link to whole dataset: https://vaers.hhs.gov/data/datasets.html?
- Link to the 2021 dataset: https://vaers.hhs.gov/eSubDownload/index.jsp?fn=2021VAERSData.zip

## Variable Description

Here are the brief descriptions of the variables I initially tried to include in my supervised learning models.

<!-- ### Case ID -->
<!-- - VAERS_ID: identification number -->

### Dependent variable
<!-- - DIED: Died -->
- RECOVD: Whether the vaccinee has recovered from COVID-19 vaccine side effects, can be "Y" for yes, "N" for no, and "U" for unknown.         
<!-- - DIEDAYS: Number of days (die date – vaccination date)       -->

### Independent variables

**Numeric**

- CAGE_YR: Calculated age of patient in years             
- HOSPDAYS: Number of days hospitalized                       
- NUMDAYS: Number of days (onset date – vaccination date)               


**Categorical**

- STATE: The home state of the vaccinee            
- SEX: Sex             
- ER_VISIT: Emergency room or doctor visit            
- HOSPITAL: Hospitalized            
- X_STAY: Prolongation of existing hospitalization            
- DISABLE: Disability            
- V_ADMINBY: Type of facility where vaccine was administered             
- V_FUNDBY: Type of funds used to purchase vaccines            
- BIRTH_DEFECT: Congenital anomaly or birth defect               
- OFC_VISIT: Doctor or other healthcare provider office/clinic visit             
- ER_ED_VISIT: Emergency room/ department or urgent care               
<!-- - SPLTTYPE: Manufacturer/immunization project report number            -->   
<!-- - FORM_VERS: VAERS form version 1 or 2          -->
- VAX_MANU: Vaccine manufacturer                 
- VAX_LOT: Manufacturer’s vaccine lot              
- VAX_DOSE_SERIES: Number of doses administered           
- VAX_ROUTE: Vaccination route              
- VAX_SITE: Vaccination site                
<!-- - VAX_NAME: Vaccination name         -->           


**Date**

- RECVDATE: Date report was received
<!-- - DATEDIED: Date of death -->
- VAX_DATE: Vaccination date
<!-- - TODAYS_DATE: Date Form Completed -->

<!-- **Text Data** -->
<!-- (tokenized) -->
<!-- - SYMPTOM_TEXT: Reported symptom text  -->
<!-- - L_THREAT: Life-threatening illness -->
<!-- - LAB_DATA: Diagnostic laboratory data -->
<!-- - OTHER_MEDS: Other medications -->
<!-- - CUR_ILL: Illnesses at time of vaccination -->
<!-- - HISTORY: Chronic or long-standing health conditions -->
<!-- - PRIOR_VAX: Prior vaccination event information -->
<!-- - ALLERGIES: Allergies to medications, food, or other products -->

*See more detailed variable descriptions here: https://vaers.hhs.gov/docs/VAERSDataUseGuide_en_September2021.pdf

# Results

Among Penalized Logistic Regression Model, Multivariate Adaptive Regression Spline, Random Forest Model, Penalized Single layer Neural Network Model (as representatives of linear models, regression splines models, tree models and neural networks), my **random forest model** (min_n = 23) performed the best prediction with the same prep-processed data -- it could predict the recovery state of the vaccinee with around 75% accuracy.


# Future directions

By using only the eligible numeric and categorical variables in this data set, I was not able to predict the recovery state of a vaccinee reported COVID-19 vaccine side effect very well, only end up with a best classification accuracy of 75% or so. There is some important information not used here describing the symptoms the vaccinee had, as well as past medical record, allergies and so on. I'll try to improve the prediction accuracy by utilizing the information in those text variables, with a combination of supervised learning and NLP methods.
