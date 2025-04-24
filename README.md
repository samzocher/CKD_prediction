# CKD_prediction

Using the All of Us dataset, I built a classification model for patients to predict whether someone has chronic kidney disease(CKD). 

30 features were engineered from EHR, genomic, demographic, and survey data. 

Included in those features is a PRS score, calculated from a previous GWAS on CKD by Wutte et al. The beta coefficient was multiplied by the # of allele copies each patient possessed for each relevant SNP (with a p < 5x10^-8). 

The goal was to optimize recall to avoid missing patients with CKD. False negatives could have a very negative clinical significance. 

My best recall-performing model was an XGBoost model with tuned hyperparameters. It utilized 25 out of the 30 features I engineered. 
Hypertension was the most predictive feature, followed by creatinine value, anemia as a comorbidity. 
Recall: 0.82
F1 score: 0.64
