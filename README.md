# Predicting Patient Readmission within 30 Days  

Unplanned hospital readmissions within 30 days of discharge pose a significant challenge in healthcare, impacting patient outcomes and driving up costs. This project applies machine learning to predict which patients are at higher risk of readmission before discharge, enabling targeted interventions and optimized resource allocation.  

---

## Datasets  

- **MIMIC-III (Medical Information Mart for Intensive Care III)**  
  - Critical care database with diagnoses, procedures, ICU stays, labs, demographics, and admissions.  
  - Used to engineer temporal, clinical, and demographic features.  

- **UCI Diabetes 130-US Hospitals Dataset**  
  - Focused on diabetic patients, including demographics, admission details, diagnostic codes, and medication changes.  

---

## Data Preprocessing and Feature Engineering  

Key engineered features include:  
- Length of stay (hospitalization duration).  
- Previous admissions and days since last discharge.  
- ICU length of stay and counts of lab events, procedures, and diagnoses.  
- Age at admission and gender.  
- Medication complexity and changes (diabetes dataset).  

Missing values were handled with pragmatic defaults (e.g., `fillna(0)`), and normalization/scaling was applied where needed.  

---

## Exploratory Data Analysis (EDA)  

Findings included:  
- Longer hospital/ICU stays and more procedures correlate with higher readmission risk.  
- Shorter recovery periods between admissions strongly predict readmission.  
- Medication changes and insulin adjustments increase readmission risk for diabetic patients.  
- Female patients showed slightly higher readmission rates; older patients had marginally higher risk.  
- Readmission rates: approximately 5.5% (MIMIC) vs. 11.2% (Diabetes dataset).  

---

## Models Implemented  

- Logistic Regression: Baseline model, interpretable and computationally efficient.  
- Random Forest Classifier: Handles non-linearities and provides feature importance.  
- XGBoost: Strong performance on structured healthcare data.  
- Neural Networks (planned): For capturing complex, non-linear interactions at scale.  

**Evaluation Metrics:** Accuracy, Precision, Recall, F1-score, and ROC-AUC (with emphasis on F1 and AUC due to class imbalance).  

---

## Results and Key Insights  

- Readmitted patients had longer hospital stays, more diagnoses, and more frequent prior admissions.  
- Diabetic patients had a higher readmission risk, particularly when medication regimens changed.  
- Seasonal fluctuations in readmission were minor but present.  
- Findings are based on randomized subsets of MIMIC-III due to computational constraints.  

---

## Real-World Applications  

- Risk stratification: Predict readmission risk at discharge.  
- Targeted interventions: Early follow-ups, enhanced discharge counseling, medication reconciliation, and home care referrals.  
- Resource optimization: Direct hospital resources toward high-risk patients.  
- Clinical decision support: Explainable predictions (via SHAP/LIME) to guide clinical judgment.  

---

## Challenges  

- Class imbalance (low readmission rates vs. majority non-readmissions).  
- Data complexity in MIMIC-III requiring careful joins across tables.  
- Computational constraints limited analysis to subsets of data.  
- Missing data handled pragmatically but could benefit from advanced imputation methods.  

---

## Tech Stack  

- Python (pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn)  
- Jupyter Notebooks for analysis and visualization  
- Planned: SHAP, LIME for interpretability  
